<template>
    <div>
        <!-- <h1>{{name}}</h1> -->
        <h1>Child Components</h1>
        <h3 v-for="user in users" :key="user.name">
            {{ user.name }} -- {{ user.email }}
        </h3>
    </div>
</template>

<script>
export default {
    name: "child-s",
    props: ['users']
    
};
</script>