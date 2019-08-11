<template>
  <div id="app">
    <div class="container">
      <router-view></router-view>
    </div>
    <Topbar />
    <Sidebar />
  </div>
</template>

<script>
import Sidebar from './components/Sidebar'
import Topbar from './components/Topbar'
export default {
  name: 'app',
  components:{ 
    Sidebar,
    Topbar
  }
}
</script>
<style>
  router-view{
    float: right;
  }
</style>
