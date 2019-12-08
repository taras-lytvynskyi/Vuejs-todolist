<template>
    <div id="app">
        <Login/>
    </div>
</template>

<script>
    import Login from "./components/Login";

    export default {
        name: 'app',
        components: {
            Login
        },
        methods: {

        }
    }
</script>

<style scoped>
    #app {
        text-align: center;
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
    }

    a {
        text-decoration: none;
        color: black;
    }

</style>


