<template>
 <h1>Ninja Reaction Timer</h1>
 <button @click="start" :disabled="isPlaying" >play</button>

  <Block v-if="isPlaying" :delay = "delay"/>


</template>


<script>

import Block from './components/Bloc.vue'

export default {
  name: 'App',
  components: { 
    Block
  }, 
  data() {
    return {
      isPlaying: false, 
      delay: null
    }
  }, 
  methods: {
    start(){
      this.delay = 2000 + Math.random() * 5000;
      this.isPlaying = true;
      console.log(this.delay)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
