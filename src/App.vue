<template>
  <div class="app-container">
    <div class="chords-container">
    <GuitarChord class="guitar-chord" 
      name="Major 7M △" 
      :openStrings='[]' 
      firstFinger="50" 
      secondFinger="10" 
      thirdFinger="12" 
      fourthFinger="22" 
      :barre='{position: "", cells: []}' 
      :deadStrings='["0", "4"]'
    />
    <GuitarChord class="guitar-chord" 
      name="Major 7m" 
      :openStrings='[]'
      firstFinger="" 
      secondFinger="21" 
      thirdFinger="42" 
      fourthFinger="" 
      :barre='{position: "0", cells: ["0", "1", "2", "3", "4", "5"]}' 
      :deadStrings='[]'
    />
    <GuitarChord class="guitar-chord" 
      name="Minor 7m" 
      :openStrings='[]'
      firstFinger="" 
      secondFinger="" 
      thirdFinger="42" 
      fourthFinger="" 
      :barre='{position: "0", cells: ["0", "1", "2", "3", "4", "5"]}' 
      :deadStrings='[]'
    />
    <GuitarChord class="guitar-chord" 
      name="Major 7M △" 
      :openStrings='[]'
      firstFinger="" 
      secondFinger="21" 
      thirdFinger="32" 
      fourthFinger="12" 
      :barre='{position: "0", cells: ["0", "1", "2", "3", "4"]}' 
      :deadStrings='["5"]'
    />
    <GuitarChord class="guitar-chord" 
      name="Major 7m" 
      :openStrings='[]'
      firstFinger="" 
      secondFinger="" 
      thirdFinger="32" 
      fourthFinger="12" 
      :barre='{position: "0", cells: ["0", "1", "2", "3", "4"]}' 
      :deadStrings='["5"]'
    />
    <GuitarChord class="guitar-chord" 
      name="Minor 7m" 
      :openStrings='[]'
      firstFinger="" 
      secondFinger="" 
      thirdFinger="32" 
      fourthFinger="11" 
      :barre='{position: "0", cells: ["0", "1", "2", "3", "4"]}' 
      :deadStrings='["5"]'
    />
    <GuitarChord class="guitar-chord" 
      name="Minor 7m (half diminished) Ø" 
      :openStrings='[]'
      firstFinger="10" 
      secondFinger="51" 
      thirdFinger="21" 
      fourthFinger="31" 
      :barre='{position: "", cells: []}' 
      :deadStrings='["0","4"]'
    />
    <GuitarChord class="guitar-chord" 
      name="Minor 7m (half diminished) Ø" 
      :openStrings='[]'
      firstFinger="40" 
      secondFinger="20" 
      thirdFinger="31" 
      fourthFinger="11" 
      :barre='{position: "", cells: []}' 
      :deadStrings='["0","5"]'
    />
    <GuitarChord class="guitar-chord" 
      name="Minor 6" 
      :openStrings='[]'
      firstFinger="11" 
      secondFinger="21" 
      thirdFinger="30" 
      fourthFinger="51" 
      :barre='{position: "", cells: []}' 
      :deadStrings='["0", "4"]'
    />
    </div>
    <div class="contact">
      <a href="https://www.youtube.com/channel/UC0paZQh-P3ruttlq26UmNig" target=”_blank”><font-awesome-icon :icon="['fab', 'youtube']"/></a> <a href="https://www.instagram.com/ivangk.gk/" target=”_blank”><font-awesome-icon :icon="['fab', 'instagram']"/></a> <a href="https://github.com/istng" target=”_blank”><font-awesome-icon :icon="['fab', 'github']"/></a> <a href="mailto:ivanstng@gmail.com"><font-awesome-icon :icon="['far', 'envelope']"/></a>
    </div>
  </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faInstagram, faYoutube, faGithub } from '@fortawesome/free-brands-svg-icons';
import { faEnvelope } from '@fortawesome/free-regular-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
library.add(faInstagram);
library.add(faYoutube);
library.add(faGithub);
library.add(faEnvelope);
import GuitarChord from './components/GuitarChord.vue'

export default {
  name: 'App',
  components: {
    FontAwesomeIcon,
    GuitarChord
  }
}
</script>

<style>
body, 
html {
  margin: 0;
  border: 0;
  padding: 0;
  margin-bottom: 100px;
}
body {
  src: url("https://fonts.googleapis.com/css2?family=Noto+Sans+JP:wght@300&display=swap");
  font-family: "Noto Sans JP", sans-serif;
  background-color: #3b463a;
  color: white;
}
.app-container {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 100px;
}
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
.contact {
  margin-top: 0.6rem; 
  margin-bottom: 0.6rem; 
  color: #e9a44d;
  word-spacing: 0.8rem;
}
a, a:hover, a:visited, a:active {
  color: inherit;
  text-decoration: none;
 }
</style>
