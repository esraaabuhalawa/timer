<template>
  <div>
  <nav >
    <router-link to="/">Home</router-link>
    <router-link :to="{name: 'about'}">About</router-link>
    <router-link :to="{name: 'timerGame'}">Timer Game</router-link>
    <router-link :to="{name: 'jobs'}"> Jobs </router-link>
  </nav>
    

    <button @click="redirect()">Redirect</button>
    <button @click="back">Go Back</button>
    <button @click="forward">Go Forward</button>
    <router-view/>
    <footer-item></footer-item>
  </div>
</template>

<script>
import FooterItem from '../src/components/FooterItem.vue'
  export default{
    components:{'footer-item' : FooterItem},
    methods:{
      redirect(){
        this.$router.push({name: 'jobs'})
      },
      back(){
        this.$router.go(-1)
      },
      forward(){
        this.$router.go(1)
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
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
  text-decoration: none;
  padding: 5px 10px;
  transition: all 0.5s ease-in-out;
}

nav a.router-link-exact-active {
  color: #42b983;
}
nav a:hover{
  color: #337cc4;
}
button{
  padding: 10px 12px;
  border: none;
  border-radius: 5px;
  margin-right: 10px;
  color: #fff;
  background: #337cc4;;
}
button:hover{
  cursor: pointer;
  background: #2c3e50;
}
</style>
