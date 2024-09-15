<template>
  <h1>HATTORI THE NINJA</h1>
  <h3>REACTION GAME</h3>
  <p>Let's see you're worthy</p>

  <button @click="start" :disabled="isPlaying" >Start</button>

  <UseBlock v-if="isPlaying" :delay="delay" />

</template>

<script>

import UseBlock from './components/useBlock.vue';


export default {
  name: 'App',
  components: {
    UseBlock
  },
  data(){
    return{
      isPlaying:false,
      delay:null
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #251372;
  text-shadow:2px 2px rgba(0, 0, 0, 0.3);
  margin-top: 60px;
}
</style>
