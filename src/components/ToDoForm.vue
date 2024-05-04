<template>
    
    <form @submit.prevent="onsubmit">
        <label for="new-todo-input"> What's needs to be done? </label>
        <input 
        type="text"
        name="new-todo" 
        id="new-todo-input"
        autocomplete="off"
        v-model.lazy.trim="label" />
        <button type="submit">Add</button>
    </form>
</template>

<script>
export default {
    methods: {
        onsubmit() {  // Add the onsubmit method to the component that emits the todo-added event with the label value. 
            
            if (this.label === "") {  // Add a condition to check if the label is empty and return if it is. 
                return;
            }
            
            this.$emit("todo-added", this.label);  // Emit the todo-added event with the label value. 
            
            this.label = ""; // Reset the label value to an empty string. 
        },
    },
   
    data() {  // Add the label data property to the component that stores the value of the input field. 
        return {
            
            label: "",  // Add the label data property to the component that stores the value of the input field. 
        };
    },
}
</script>