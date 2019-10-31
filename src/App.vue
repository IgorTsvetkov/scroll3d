<template>
  <div id="app">
    <scroll360>
      <img src="./../images/MAZ_1.jpg"/>
      <img src="./../images/MAZ_2.jpg"/>
      <img src="./../images/MAZ_3.jpg"/>
      <img src="./../images/MAZ_4.jpg"/>
      <img src="./../images/MAZ_5.jpg"/>
      <img src="./../images/MAZ_6.jpg"/>
      <img src="./../images/MAZ_7.jpg"/>
      <img src="./../images/MAZ_8.jpg"/>
      <img src="./../images/MAZ_9.jpg"/>
      <img src="./../images/MAZ_10.jpg"/>
      <img src="./../images/MAZ_11.jpg"/>
    </scroll360>
  </div>
</template>

<script>
import scroll360 from './components/scroll360.vue'

export default {
  name: 'app',
  components: {
    scroll360
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
