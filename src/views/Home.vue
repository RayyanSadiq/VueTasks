<template>
    <div v-show="showAddTask" >
     <AddTask @add-task="addTask" />
   </div>
   
   <Tasks @delete-task="deleteTask" @toggle-reminder="toggleReminder" :tasks="tasks" />
</template>

<script>
import Tasks from '../components/Tasks.vue'
import AddTask from '../components/AddTask.vue'

export default {
    
   props: {
    showAddTask: Boolean
   },
    components: {
        Tasks,
        AddTask
    },
    data () {
        return {
            tasks: []
        }
    }, 
    methods: {
      async addTask(task) {
        task.id = task.id.toString()
        const response = await fetch('api/tasks', {
          method: 'POST',
          headers: {
            'Content-type': 'application/json',
           
          },
          body: JSON.stringify(task)
        })
        const data = await response.json()
        console.log(this.tasks)

        this.tasks.push(data)
      },
      async deleteTask(id){
        if(confirm('Are you sure you want to delete this task?')){
          const response = await fetch(`api/tasks/${id}`, {method: 'DELETE'})
          
          if (response.status === 200 ) {
            this.tasks = this.tasks.filter(task => task.id !== id)
          }
          else {
            alert('Error Deleting Task')
          }
          
        }
        
      },
      async toggleReminder(id){
        const taskToToggle = await this.fetchTask(id)
        taskToToggle.reminder = !taskToToggle.reminder  
        
        const response = await fetch(`api/tasks/${id}`, {
          method: 'PUT', 
          headers: {'Content-type': 'application/json'},
          body: JSON.stringify(taskToToggle)
        })

        const data = await response.json()

        this.tasks.forEach(task => {
          if(task.id === id){
            task.reminder = data.reminder
          }
        })
      },
      async fetchTasks() {
        const response = await fetch ('api/tasks');

        const data = await response.json()
        return data;
      },
      async fetchTask(id) {
        const response = await fetch (`api/tasks/${id}`);

        const data = await response.json()
        return data;
      }
    },
    async created() {
        this.tasks = await this.fetchTasks()
    }
}
</script>