<template>
  <div id="app">
    <h1>TO-DO List</h1>
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">
        <to-do-item 
        :label="item.label" 
        :done="item.done"
        :id="item.id"></to-do-item>
      </li>
    </ul>
  </div>
</template>

<script> 
import ToDoItem from './components/ToDoItem.vue';
import uniqueId from "lodash.uniqueid";

export default {
  name:"app",
  components: {
    ToDoItem,
  },
  data() {
    return {
      ToDoItems: [
        {id: uniqueId("todo-"), label: "Learn Vue.js", done: false},
        {
          id: uniqueId("todo-"),
          label: "Create a Vue project with the Vue CLI",
          done: true
        },
        {id: uniqueId("todo-"), label: "Have fun", done: true},
        {id: uniqueId("todo-"), label: "Create a to-do list", done: false},
      ],
    };
  },
};
</script>

<style>
</style>