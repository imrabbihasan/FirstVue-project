<template>
    <div>
        <input type="checkbox" :id="id" :checked="isDone">  // Add the input element to the template with type attribute set to checkbox, id attribute bound to the id prop, and checked attribute bound to the isDone data property. 
        <label :for="id">{{label}}</label>  // Add the label element to the template with for attribute bound to the id prop and text content bound to the label prop.
    </div>
</template>
<script>
export default {
    props: {
        label: {required: true, type: String},  // Add the label prop to the component with required set to true and type set to String.
        done: {default: false, type: Boolean},  // Add the done prop to the component with default set to false and type set to Boolean.
        id: {required: true, type: String},  // Add the id prop to the component with required set to true and type set to String.
    },
    data() {
        return {
            isDone: this.done,  // Add the isDone data property to the component with an initial value of the done prop value.
        };
    },
};
</script>
