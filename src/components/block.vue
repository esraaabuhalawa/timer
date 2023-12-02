<template>
    <div class="block" v-if="showBlock" @click="stopTimer()">
      click me
    </div>
    
  </template>
  
<script>
  export default ({
  name: 'block',
  props : ['delay'],
  data(){
    return{
      showBlock: false,
      timer : null,
      timeReaction :0
    }
  },
  components: {
  },
  mounted(){
    setTimeout(() => {
      this.showBlock = true;
      this.startTimer()
    }, this.delay)
  },
  methods:{
    startTimer(){
      this.timer = setInterval(()=>{
        this.timeReaction += 10;
      }, 10)
    },
    stopTimer(){
      clearInterval(this.timer)
      this.$emit('end',this.timeReaction)
    }
  }

});
</script>

<style>
  .block{
    margin: 40px auto;
    padding: 100px 0;
    text-align: center;
    width: 400px;
    background: #15848c;
    border-radius: 15px;
    font-size: 25px;
    color: #fff;
  }
</style>
