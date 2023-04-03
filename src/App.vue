<template>
  <div id="app">
    <TaskList />
  </div>
  <div class="text-center mt-5">
      <p>by alexander</p>
  </div>
</template>
<style>
@import '~bootstrap/dist/css/bootstrap.css';
</style>
<script>
import TaskList from './components/TaskList.vue';

export default {
  name: 'App',
  components: {
    TaskList,
  },
};
</script>
