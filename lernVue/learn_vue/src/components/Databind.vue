<template>
    <div class="bind">
        <h1 class="msgH1">{{message}}</h1>
        <textarea type="text" v-model="message"/>
    </div>
</template>

<script>
export default{
    name: 'Data-bind',
    data(){
        return{
            message:'Hi'
        }
    }
}
</script>


<style>

.bind{
    background-color: rgb(150, 206, 254);
    width: 700px;
    height: 400px;
    margin: auto;
}

.msgH1{
    white-space:pre-line
}
</style>