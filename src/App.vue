<template>
  <div id="app">
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <Ad msg="Welcome to Your Vue.js App"/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Ad from './components/Ad.vue'

export default {
  name: 'App',
  components: {
    Ad
  }
}
</script>

<style>
body {
 background-image: url("https://kad.events.104.com.tw/t-ambassador_20210826/img/joinNowBg@2x.27604b50.png");
 background-color: #cccccc;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
