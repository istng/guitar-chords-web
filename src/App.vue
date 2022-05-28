<template>
  <div class="app-container">
    <div class="chords-container">
      <GuitarChord v-for="guitarChord in guitarChords" class="guitar-chord" 
        :name='guitarChord.name' 
        :openStrings='guitarChord.openStrings' 
        :firstFinger='guitarChord.firstFinger' 
        :secondFinger='guitarChord.secondFinger' 
        :thirdFinger='guitarChord.thirdFinger' 
        :fourthFinger='guitarChord.fourthFinger' 
        :barre='guitarChord.barre' 
        :deadStrings='guitarChord.deadStrings'
        v-bind:key='guitarChord.name'
      />
    </div>
    <div class="scales-container">
      <GuitarScale class="guitar-scale" :name='"Mayor Scale"' :scale='[1,0,2,0,3,4,0,5,0,6,0,7]' />
      <GuitarScale class="guitar-scale" :name='"Minor Scale"' :scale='[1,0,2,3,0,4,0,5,6,0,7,0]' />
    </div>
    <div class="contact">
      <a href="https://ivangk.web.app" target=”_blank”><font-awesome-icon :icon="['fas', 'user']"/></a> <a href="https://www.youtube.com/channel/UC0paZQh-P3ruttlq26UmNig" target=”_blank”><font-awesome-icon :icon="['fab', 'youtube']"/></a> <a href="https://www.instagram.com/ivangk.gk/" target=”_blank”><font-awesome-icon :icon="['fab', 'instagram']"/></a> <a href="https://github.com/istng" target=”_blank”><font-awesome-icon :icon="['fab', 'github']"/></a>
    </div>
  </div>
</template>

<script>
import { library } from '@fortawesome/fontawesome-svg-core';
import { faInstagram, faYoutube, faGithub } from '@fortawesome/free-brands-svg-icons';
import { faUser } from '@fortawesome/free-solid-svg-icons'
import { FontAwesomeIcon } from '@fortawesome/vue-fontawesome';
library.add(faInstagram);
library.add(faYoutube);
library.add(faGithub);
library.add(faUser);
import GuitarChord from './components/GuitarChord.vue';
import GuitarScale from './components/GuitarScale.vue'
import { guitarChords } from './variables/chords.js';

export default {
  name: 'App',
  components: {
    FontAwesomeIcon,
    GuitarChord,
    GuitarScale
  },
  setup() {
    return {
      guitarChords
    };
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
.scales-container {
  display: flex;
  gap: 25px;
  flex-wrap: wrap;
  justify-content: center;
  align-items: center;
}
.guitar-scale {
  flex-basis: 300px;
}
.contact {
  margin-top: 0.6rem; 
  margin-bottom: 0.6rem; 
  color: white;
  word-spacing: 0.8rem;
}
a, a:hover, a:visited, a:active {
  color: inherit;
  text-decoration: none;
 }
</style>
