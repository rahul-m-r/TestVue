<template>
  <div id="app">
    <div class="hc">
      <NotificationBar/>
      <NavBar/>
    </div>
    <SearchBar/>
    <Slider/>
  </div>
</template>

<script>
import NotificationBar from './components/NotificationBar'
import Slider from './components/Slider'
import NavBar from './components/NavBar'
import SearchBar from './components/SearchBar'

export default {
  name: 'App',
  components: {
    NotificationBar,
    Slider,
    NavBar,
    SearchBar
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
.hc {
  position:fixed; 
  z-index: 100; 
  width: 100%;
}
</style>
