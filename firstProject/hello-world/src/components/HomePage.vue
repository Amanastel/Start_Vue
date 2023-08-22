<template>
  <div>
    <h1>Hello home from components </h1>
    <h2>{{msg}}</h2>
    <h1>Simple Counter App</h1>
    <p>Count: {{ count }}</p>
    <button @click="increment">Increment</button>
    <button @click="decrement">Decrement</button>
  </div>
</template>

<script>
export default {
  name: 'HomePage',
  props: {
    msg:String
  },
  data() {
    return {
      count: 0
    };
  },
  methods: {
    increment() {
      this.count++;
    },
    decrement() {
      if (this.count > 0) {
        this.count--;
      }
    }
  }
  
}
</script>

