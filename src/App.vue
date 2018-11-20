<template>
  <div id="app">
    <center>
    <h1>Parcial 2</h1>
    <p>Carlos Canto 8-896-2125</p>
    </center>
   <login/>
   
  </div>
</template>

<script>
import login from './components/Login.vue'

export default {
  name: 'app',
  components: {
    login
  }
}
</script>
