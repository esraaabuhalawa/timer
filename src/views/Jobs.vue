<template>
  <div v-if="jobs.length">
    <h2>Jobs</h2>
    <div v-for="job in jobs" :key="job.id" class="jobs">
        <router-link :to="{name : 'JobsDetails' , params:{id : job.id}}">
          <h3>{{ job.name }}</h3>
           <p>{{ job.position }}</p>
        </router-link>
        
    </div>
  </div>
  <div v-else><p>Job details are loading ...</p></div>
</template>

<script>
export default {
    data(){
        return{
            jobs: []
        }
    },
    mounted(){
      fetch('http://localhost:3000/jobs')
      .then((res) => res.json()).then(data => {
        this.jobs = data
        console.log(data)
      })
    }
}
</script>

<style scoped>
h2{
    margin-top: 5rem;
    font-size: 2.5rem;
}
.jobs{
  background: wheat;
  width: 50%;
  margin: 10px auto;
  padding: 15px;
}
.jobs h3 {
    font-size: 18px;
   
   


}
.jobs a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 5px 10px;
  transition: all 0.5s ease-in-out;
}

.jobs a.router-link-exact-active {
  color: #42b983;
}
.jobs a:hover{
  color: #337cc4;
}
</style>