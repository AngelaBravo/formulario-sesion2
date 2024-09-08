<template>
  <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
  <SessionDosForm msg="Formulario Session 2"/>

</template>

<script>
import SessionDosForm from './components/SessionDosForm.vue'

export default {
  name: 'App',
  components: {
    SessionDosForm
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
