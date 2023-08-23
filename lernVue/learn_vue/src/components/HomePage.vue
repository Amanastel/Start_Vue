<template>
    <div>
        <h1 v-if="show">Conditional Rendring in vue js</h1>
        <h1 v-else>Conditional Rendring else vue js</h1>
        <button @click="display">Toggle</button>
    </div>
</template>

<script>
export default {
    name: 'HomePage',
    props:{
        msg: String,
        data: String,
    },
    data(){
        return{
            show:false
        }
    },
    methods:{
        display(){
            this.show=!this.show
        }
    }
}
</script>
  