<template>
    <form @submit.prevent="onsubmit">
        <label for="new-todo-input"> What's needs to be done? </label>
        <input 
        type="text"
        name="new-todo" 
        id="new-todo-input"
        autocomplete="off">
        <button type="submit">Add</button>
    </form>
</template>

<script>
export default {
    methods: {
        onsubmit() {
            console.log("Form submitted");
        }
    }
}
</script>