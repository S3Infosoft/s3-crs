<template>
  <div id="app">
    <Sidebar />
    <router-view></router-view>
  </div>
</template>

<script>
import Sidebar from './components/Sidebar'
export default {
  name: 'app',
  components:{ 
    Sidebar
  }
}
</script>
<style>
  router-view{
    float: right;
  }
</style>
