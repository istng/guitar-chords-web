<template>
  <div class="chords-container">
    <GuitarChord class="guitar-chord" firstFinger="00" secondFinger="02" thirdFinger="12" fourthFinger="52" barrePosition="1"/>
  </div>
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
.chords-container {
  display: flex;
  gap: 10px;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.guitar-chord {
  flex-basis: 300px;
}
</style>
