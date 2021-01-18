<template>
  <div id="app">
    <div id='todoApp'>
      <Header/>
      <router-view/>
    </div>
  </div>
</template>

<script>
import Header from './components/Header.vue';

export default {  
  name:"app",
  components: {
    Header
  }
}
</script>

<style>
  * {
    margin: 0;
    padding: 0;
  }

  body {
    font-family: Arial, Helvetica, sans-serif;
  }

  .btn {
    display: inline-block;
    border: none;
    background: #555;
    color: whitesmoke;
    padding: 7px 20px;
    cursor: pointer;
  }

  .btn:hover {
    background: #666;
  }

#app {
  display: flex;
  justify-content: center;
  color: #2c3e50;
  width: 100vw;
  height: 100vh;
}

#todoApp {
  border: 1px solid darkslategrey;
  width: 50vw;
  height: 100vh;
}

@media screen and (max-width: 800px) {
  #todoApp {
    width: 100vw;
    border: none;
  }
}

#nav {
  padding: 30px;
}

#nav a {
  font-weight: bold;
  color: #a3a3a3;
}

#nav a.router-link-exact-active {
  color: #fff;
}
</style>
