<template>
  <GuitarChord firstFinger="00" secondFinger="02" thirdFinger="12" fourthFinger="52" barrePosition="1"/>
</template>

<script>
import GuitarChord from './components/GuitarChord.vue'

export default {
  name: 'App',
  components: {
    GuitarChord
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
  margin-top: 60px;
}
/*body, html {
  border: 0;
  padding: 0;
  margin: 0;
}*/
</style>
