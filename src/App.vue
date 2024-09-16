<template>
  <h1>HATTORI THE NINJA</h1>
  <h3>REACTION GAME</h3>
  <p>Let's see you're worthy</p>

  <button @click="start" :disabled="isPlaying" >Start</button>

  <UseBlock v-if="isPlaying" :delay="delay" @end="endGame" />

  <use-result v-if="showResult" :score="score" />

</template>

<script>

import UseBlock from './components/useBlock.vue';
import UseResult from './components/useResult.vue';


export default {
  name: 'App',
  components: {
    UseBlock,
    UseResult
  },
  data(){
    return{
      isPlaying:false,
      delay:null,
      score:null,
      showResult:false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000
      this.isPlaying = true
      this.showResult=false
    },
    endGame(reactionTime){
      this.score=reactionTime
      this.isPlaying=false
      this.showResult=true
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
  color: rgb(242, 234, 234);
  text-shadow:0.2ch 0.3ch rgba(0, 0, 0, 0.9);
  margin-top: 60px;
}
body{
  background: linear-gradient(90deg, #0800ffd3, rgb(184, 162, 255))
}
p{
  font-weight: 500;
}
</style>
