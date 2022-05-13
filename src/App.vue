<template>
  <div class="chords-container">
  <GuitarChord class="guitar-chord" openString="5" firstFinger="00" secondFinger="12" thirdFinger="22" fourthFinger="42" :barre='{position: "1", cells: ["0","1","2","3","4"]}' :deadStrings='[]'/>
<GuitarChord class="guitar-chord" openString="4" firstFinger="00" secondFinger="12" thirdFinger="22" fourthFinger="42" :barre='{position: "1", cells: ["0","1","2","3","4"]}' :deadStrings='["4","5"]' />
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
  gap: 25px;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.guitar-chord {
  flex-basis: 300px;
}
</style>
