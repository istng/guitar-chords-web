<template>
  <div class="chord">
    <div class="frets">
      <div class="first-second-fret fret"></div>
      <div class="empty-fret"></div>
      <div class="third-fourth-fret fret"></div>
    </div>
    <div class="strings">
      <div class="first-cell first-string"><hr class="string"><div class="finger position-0" id="finger-00"></div></div>
      <div class="second-cell first-string"><hr class="string"><div class="finger position-1" id="finger-01"></div></div>
      <div class="third-cell first-string"><hr class="string"><div class="finger position-2" id="finger-02"></div></div>
      
      <div class="first-cell second-string"><hr class="string"><div class="finger position-0" id="finger-10"></div></div>
      <div class="second-cell second-string"><hr class="string"><div class="finger position-1" id="finger-11"></div></div>
      <div class="third-cell second-string"><hr class="string"><div class="finger position-2" id="finger-12"></div></div>

      <div class="first-cell third-string"><hr class="string"><div class="finger position-0" id="finger-20"></div></div>
      <div class="second-cell third-string"><hr class="string"><div class="finger position-1" id="finger-21"></div></div>
      <div class="third-cell third-string"><hr class="string"><div class="finger position-2" id="finger-22"></div></div>

      <div class="first-cell fourth-string"><hr class="string"><div class="finger position-0" id="finger-30"></div></div>
      <div class="second-cell fourth-string"><hr class="string"><div class="finger position-1" id="finger-31"></div></div>
      <div class="third-cell fourth-string"><hr class="string"><div class="finger position-2" id="finger-32"></div></div>

      <div class="first-cell fifth-string"><hr class="string"><div class="finger position-0" id="finger-40"></div></div>
      <div class="second-cell fifth-string"><hr class="string"><div class="finger position-1" id="finger-41"></div></div>
      <div class="third-cell fifth-string"><hr class="string"><div class="finger position-2" id="finger-42"></div></div>

      <div class="first-cell sixth-string"><hr class="string"><div class="finger position-0" id="finger-50"></div></div>
      <div class="second-cell sixth-string"><hr class="string"><div class="finger position-1" id="finger-51"></div></div>
      <div class="third-cell sixth-string"><hr class="string"><div class="finger position-2" id="finger-52"></div></div>
    </div>
  </div>
</template>

<script>

function styleChanger(element, styles) {
  Object.entries(styles).forEach((style) => {
    element.style[style[0]] = style[1];
  });
}

import {
  onMounted
} from "vue";
export default {
  name: 'GuitarChord',
  props: {
    firstFinger: String,
    secondFinger: String,
    thirdFinger: String,
    fourthFinger: String,
    barrePosition: String
  },
  setup(props) {

    onMounted(() => {
      document.getElementById("finger-"+props.firstFinger).innerText = "1";
      document.getElementById("finger-"+props.secondFinger).innerText = "2";
      document.getElementById("finger-"+props.thirdFinger).innerText = "3";
      document.getElementById("finger-"+props.fourthFinger).innerText = "4";

      var fingerStyle = {
        "background-color": "red",
        "border-radius": "100%",
        "padding": "5%",
        "color": "white"
      }

      styleChanger(document.getElementById("finger-"+props.firstFinger), fingerStyle);
      styleChanger(document.getElementById("finger-"+props.secondFinger), fingerStyle);
      styleChanger(document.getElementById("finger-"+props.thirdFinger), fingerStyle);
      styleChanger(document.getElementById("finger-"+props.fourthFinger), fingerStyle);

      var barreStyle = {
        "border-left": "6px solid blue",
        "height": "100%"
      }

      Array.from(document.getElementsByClassName("position-"+props.barrePosition)).forEach((position) => {
        styleChanger(position, barreStyle);
      });
    });
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.chord {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-template-rows: repeat(1, 1fr);
}

.frets {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(1, 1fr);
  grid-column: 1 / 1;
  grid-row: 1 / 1;
}
.fret {
  border-left: 6px solid green;
  border-right: 6px solid green;
  height: 100%;
}
.first-fret {
  align-self: center;
  justify-self: start;
}
.second-fret, .third-fret {
  align-self: center;
  justify-self: start;
}
.fourth-fret {
  align-self: center;
  justify-self: end;
}

.strings {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: repeat(6, 1fr);
  grid-column: 1 / 1;
  grid-row: 1 / 1;
}
.first-cell, .second-cell, .third-cell {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-template-rows: repeat(1, 1fr); 
}
.string {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
  width: 100%;
  align-self: center;
  justify-self: stretch;
}
.finger {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
  align-self: center;
  justify-self: center;
}
</style>
