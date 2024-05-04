<template>
  <div id="app">
    <h1>TO-DO List</h1>
    <to-do-form @todo-added="addToDo"></to-do-form>  
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
import ToDoItem from './components/ToDoItem.vue';  // Import the ToDoItem component
import uniqueId from "lodash.uniqueid";  // Import the uniqueId function from the lodash library
import ToDoForm from "./components/ToDoForm.vue";  // Import the ToDoForm component


export default {
  name:"app",
  // Register the ToDoItem and ToDoForm components in the parent component
  components: {
    ToDoItem, ToDoForm,  // Register the ToDoItem and ToDoForm components
  },
  data() {
    return {
      // Add a new ToDoItems array to the data object that contains the to-do items. 
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
  // Add the addToDo method to the component that adds a new to-do item to the ToDoItems array.
  methods: {
    addToDo(toDoLabel) {  // Add the addToDo method to the component that adds a new to-do item to the ToDoItems array. 
      this.ToDoItems.push({   // Add a new to-do item object to the ToDoItems array with the provided label and default done value of false. 
        id: uniqueId("todo-"),  // Generate a unique ID for the new to-do item using the uniqueId function. 
        label: toDoLabel,   // Add the provided to-do label to the new to-do item object. 
        done: false,  // Set the done property of the new to-do item object to false by default. 
      });
    }
  }
};
</script>

<style>
</style>