<template>
  <div class="chord">
    <div class="frets">
      <div class="first-second-fret fret"></div>
      <div class="empty-fret"></div>
      <div class="third-fourth-fret fret"></div>
    </div>
    <div class="strings">
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-00"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-01"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-02"></div></div>
      
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-10"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-11"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-12"></div></div>

      <div class="string-cell"><hr class="string"><div class="cell" id="cell-20"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-21"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-22"></div></div>

      <div class="string-cell"><hr class="string"><div class="cell" id="cell-30"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-31"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-32"></div></div>

      <div class="string-cell"><hr class="string"><div class="cell" id="cell-40"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-41"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-42"></div></div>

      <div class="string-cell"><hr class="string"><div class="cell" id="cell-50"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-51"></div></div>
      <div class="string-cell"><hr class="string"><div class="cell" id="cell-52"></div></div>
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
    barre: Object
  },
  setup(props) {

    onMounted(() => {
      document.getElementById("cell-"+props.firstFinger).innerText = "1";
      document.getElementById("cell-"+props.secondFinger).innerText = "2";
      document.getElementById("cell-"+props.thirdFinger).innerText = "3";
      document.getElementById("cell-"+props.fourthFinger).innerText = "4";

      var cellStyle = {
        "background-color": "red",
        "border-radius": "100%",
        "padding": "5%",
        "color": "white"
      }

      styleChanger(document.getElementById("cell-"+props.firstFinger), cellStyle);
      styleChanger(document.getElementById("cell-"+props.secondFinger), cellStyle);
      styleChanger(document.getElementById("cell-"+props.thirdFinger), cellStyle);
      styleChanger(document.getElementById("cell-"+props.fourthFinger), cellStyle);
      console.log(props.barre)

      var barreStyle = {
        "border-left": "6px solid blue",
        "height": "100%"
      }
      props.barre.cells.forEach((cell) => {
        styleChanger(document.getElementById("cell-"+cell+props.barre.position), barreStyle);
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
.string-cell {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-template-rows: repeat(1, 1fr); 
}
.string {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
  width: 100%;
  height: 0;
  align-self: center;
  justify-self: stretch;
}

.cell {
  grid-column: 1 / 1;
  grid-row: 1 / 1;
  align-self: center;
  justify-self: center;
}
</style>
