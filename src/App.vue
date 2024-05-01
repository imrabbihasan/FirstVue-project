<template>
  <div id="app">
    <h1>TO-DO List</h1>
    <ul>
      <li>
        <to-do-item label="My ToDo Item"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script> 
import ToDoItem from './components/ToDoItem.vue';
export default {
  name:"app",
  components: {
    ToDoItem,
  },
};
</script>

<style>
</style>