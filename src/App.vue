<template>
  <div id="app">
    <div class="row vh-100">
      <Sidebar/>
      
      <div class="col-11">
        <BudgetList/>
      </div>
    </div>
   
  </div>
</template>

<script>
import Sidebar from './components/Sidebar.vue'
import BudgetList from './components/BudgetList.vue'

export default {
  name: 'app',
  components: {
    Sidebar,
    BudgetList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}

.vh-100 {
  height: 100vh;
}
</style>