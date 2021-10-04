<template>
  <Header title="Task Tracker"/>
  <Tasks/>
</template>

<script>
import Header from "./components/Header.vue"
import Tasks from "./components/Tasks.vue"

export default {
  name: 'App',
  components: {
    Header,
    Tasks
  }
}
</script>

<style>
#app {
  font-family: cursive, Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  max-width: 100%;
  margin: auto;
  margin-top: 15px;
}
.container {
  height: 85%;
}
</style>
