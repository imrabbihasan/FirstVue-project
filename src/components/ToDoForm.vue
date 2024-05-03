<template>
    // Add the form element to the template
    <form @submit.prevent="onsubmit">
        // Add the label input field to the form element with v-model.lazy directive to bind the input value to the label data property and trim modifier to remove whitespace from the input value before assigning it to the label property. 
        <label for="new-todo-input"> What's needs to be done? </label>
        // Add the button element to the form element with type attribute set to submit and text content Add.
        <input 
        type="text"
        name="new-todo" 
        id="new-todo-input"
        autocomplete="off"
        v-model.lazy.trim="label" />
        // Add the button element to the form element with type attribute set to submit and text content Add.
        <button type="submit">Add</button>
    </form>
</template>

<script>
export default {
    methods: {
        onsubmit() {
            // Check if the label property is an empty string. If it is, return early from the method. 
            if (this.label === "") {
                return;
            }
            // Emit the todo-added event with the label value as the payload and reset the label value to an empty string. 
            this.$emit("todo-added", this.label);
            // Reset the label value to an empty string.
            this.label = "";
        },
    },
    // Add the label data property to the component with an initial value of an empty string.
    data() {
        return {
            // Add the label data property to the component with an initial value of an empty string.
            label: "",
        };
    },
}
</script>