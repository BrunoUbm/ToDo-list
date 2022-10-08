<template>
  <div>
    <TodosComents />
  </div>
</template>

<script>
import TodosComents from './components/TodosComents.vue';

export default {
  name: 'App',
  components: {
    TodosComents,
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
