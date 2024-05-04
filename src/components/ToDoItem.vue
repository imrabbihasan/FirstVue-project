<template>
    <div>
        <input type="checkbox" :id="id" :checked="isDone">  
        <label :for="id">{{label}}</label>  
    </div>
</template>
<script>
export default {
    props: {
        label: {required: true, type: String},  // Add the label prop to the ToDoItem component that accepts a string value. 
        done: {default: false, type: Boolean},  // Add the done prop to the ToDoItem component that accepts a boolean value. 

    },
    data() {
        return {
            isDone: this.done,   // Add the isDone data property to the component that stores the value of the done prop. 
        };
    },
};
</script>
