<template>
  <div id="app">
    <TaskToDo />
  </div>
</template>

<script>
import TaskToDo from './components/TaskToDo.vue'

export default {
  name: 'App',
  components: {
    TaskToDo
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Monsterrat:400,700');
body{
background-color: #EEEEEE;
font-family: 'Monsterrat' , sans-serif;
display:grid;
grid-template-rows: auto;
justify-items: center;
align-items: center;
}
body, html {
  margin: 0;
  height: 100%;
}
#app {
  width: 50%;
}
</style>
