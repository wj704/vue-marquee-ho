<template>
  <div id="app">
    <!-- <img src="./assets/logo.png"> -->
    <div class="marquee-wrap"><vue-marquee content="222222222" class="two"  showtwo="false"></vue-marquee></div>
    <div class="marquee-wrap"><vue-marquee content="111111111" class="two"  showtwo="false"></vue-marquee></div>
    <div class="marquee-wrap"><vue-marquee content="3" class="two"  :showtwo="false" speed="quick" ></vue-marquee></div>
  </div>
</template>

<script>
// import Hello from './components/Hello'
import vueMarquee from './Marquee.vue'

export default {
  name: 'app',
  components: {
    vueMarquee
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
.marquee-wrap {
  width: 100px;
  margin: 0 auto;
}
</style>
