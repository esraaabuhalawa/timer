<template>
    <div >
      <p>The result Time is {{ score }} in ms </p>
      <p class="rank">{{ rank }} ...</p>
    </div>
    
  </template>
  
  <script>
  export default({
    name: 'result',
    props :["score"],
    data(){
      return{
        rank : null
      }
      
    },
    mounted(){
      if(this.score < 250){
        this.rank = "Swift"
      }else if(this.score < 400){
        this.rank = "Excellent"
      }else{
        this.rank = "try Again"
      }
    }
    
  });
  </script>
  
  <style scoped>
 p{color: rgb(18, 87, 102);font-size: 20px;padding: 10px 0;}
 .rank{
  font-size: 30px;
    font-weight: bold;
    padding: 10px 0;
    color: teal;
 }
  </style>
  