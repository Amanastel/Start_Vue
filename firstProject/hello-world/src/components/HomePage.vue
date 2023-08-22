<template>
  <div>
    <h1>Hello home from components </h1>
    <h2>{{msg}}</h2>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  props: {
    msg:String
  }
}
</script>
