<template>
    <header class='header'>
        <h1>TODO LIST</h1>
        <div id="nav">
            <router-link to="/">Home</router-link> |
            <router-link to="/about">Sobre</router-link>
        </div>
    </header>
</template>

<script>
export default {
    name: 'header'
}
</script>

<style scoped>
    .header {
        background: darkslategrey;
        color: whitesmoke;
        text-align: center;
        padding: 10px;
    }

    .header a {
        color: whitesmoke;
        padding-right: 5px;
        text-decoration: none;
    }
</style>