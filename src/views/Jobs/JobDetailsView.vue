<template>
    <div v-if="job">
        <h3>Job Details Page</h3>
        <h4></h4>
        <h4>{{id }}</h4>
        <p>{{ job.name }} </p>
        <p>{{ job.position }} </p>
        <p>{{ job.description }}</p>
    </div>
    <div v-else>
        <p>Loading job details ...</p>
    </div>
   
</template>

<script>
export default {
    data(){
        return{
            id: this.$route.params.id,
            job : null
        }
    },
    mounted(){
      fetch('http://localhost:3000/jobs/' + this.id)
      .then((res) => res.json()).then(data => {
        this.job = data
        console.log(data)
      })
    }
   
}
</script>

<style>

</style>