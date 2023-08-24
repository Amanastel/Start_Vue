<template>
    <div>
        <button v-on:click="updateTitle">Update Parent Title</button>
    </div>
</template>

<script>
export default {
    name: "child-2",
    methods: {
        updateTitle() {
            this.$emit('update-title', 'Updated from child component');
            
        }
    }
};
</script>