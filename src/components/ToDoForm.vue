<template>
    <form @submit.prevent="onsubmit">
        <h2 class="label-wrapper">
            <label for="new-todo-input" class="label__lg"> 
                What's needs to be done?
            </label>
        </h2>
        <input 
        type="text"
        name="new-todo" 
        id="new-todo-input"
        autocomplete="off"
        v-model.lazy.trim="label"
        class="input__lg" />
        <button type="submit" class="btn btn__primary btn__lg">Add</button>
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