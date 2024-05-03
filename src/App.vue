<template>
  <div id="app">
    <h1>TO-DO List</h1>
    <to-do-form @todo-added="addToDo"></to-do-form>  // Add the to-do-form component to the template with the todo-added event listener bound to the addToDo method.
    <ul>
      <li v-for="item in ToDoItems" :key="item.id">  // Add the li element to the template with v-for directive iterating over the ToDoItems array and binding the item.id value to the key attribute. 
        // Add the to-do-item component to the li element with the label, done, and id props bound to the item properties.
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
import ToDoForm from "./components/ToDoForm.vue";


export default {
  name:"app",
  components: {
    ToDoItem, ToDoForm,  // Add the ToDoItem and ToDoForm components to the components object.
  },
  data() {
    return {
      // Add the ToDoItems array to the data object with four to-do items.
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
    addToDo(toDoLabel) {
      this.ToDoItems.push({  // Push a new object to the ToDoItems array with a unique id, label, and done set to false.
        id: uniqueId("todo-"),  // Generate a unique id for the new to-do item.
        label: toDoLabel,  // Set the label property to the toDoLabel value.
        done: false, // Set the done property to false.
      });
    }
  }
};
</script>

<style>
</style>