<template>
    <footer>
        <p>Copyright &copy; 2024</p>
        <RouterLink to="/about">Go to About</RouterLink>
    </footer>
</template>

<script>

export default {
    name: 'Footer',
}
</script>

<style>
    a {
        color: #333;
    }

    footer {
        margin-top: 30px;
        text-align: center;
    }

</style>