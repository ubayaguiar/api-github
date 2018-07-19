<template>
  <div id="app">
    <h1>{{msg}}</h1>
    <branches/>
    <commit branch="master"/>
  </div>
</template>

<script>
import commit from './components/commit'
import branches from './components/branches'

export default {
  name: 'App',
  components: {
    branches,
    commit,
    
  }, data(){
    return{
      msg: "Latest Commits"
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
