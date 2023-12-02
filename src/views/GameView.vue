<template>
  <div>
    <h1>Reaction Timer</h1>
    <button @click="start" :disabled="isPlay">Play</button>
    <block v-if="isPlay" :delay = "delay" @end="endGame"></block>
    <results v-if="showResults" :score="score"></results>
  </div>
</template>

<script>
import Block from "../components/block.vue";
import Results from "../components/results.vue";

export default {
   // name:GameView,
    components: {
    'results':Results,
    'block':Block,
  },
  data(){
    return {
      isPlay : false,
      delay : null,
      score : null,
      showResults : false
    }
  },
  methods:{
    start(){
      this.delay = 2000 + Math.random() * 5000;
      this.isPlay = true;
      this.showResults = false
    },
    endGame(timeReaction){
      this.score = timeReaction;
      this.showResults = true
      this.isPlay = false
    }
  }
}
</script>

<style scoped>
button{
  font-size: 0.9rem;
    color: white;
    background: teal;
    border: none;
    padding: 9px 18px;
    transition: all 0.5s ease-in;
    border-radius: 5px;
}
button:hover{
  cursor: pointer;
  background: #17c5c2;
}
button:disabled{
  opacity: 0.5;
}
</style>