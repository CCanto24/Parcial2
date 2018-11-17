<template>
  <div id="app">
    <center>
    <h1>Bienvenido</h1>
    </center>
   <login/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import login from './components/Login.vue'

export default {
  name: 'app',
  components: {
    HelloWorld,
    login
  }
}
</script>
