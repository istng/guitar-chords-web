<template>
  <div class="scale-container">
    <h4 class="scale-name">{{name}}</h4>
    <div class="scale">
      <div class="frets">
        <div class="fret"></div>
        <div class="start-middle-fret"></div>
        <div class="empty-fret"></div>
        <div class="end-middle-fret"></div>
        <div class="fret"></div>
      </div>
      <div class="strings">
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("00")' :class='{cell: true, noteCell: isNoteCell("00"), tonicCell: isTonicCell("00")}'>{{cells["00"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("01")' :class='{cell: true, noteCell: isNoteCell("01"), tonicCell: isTonicCell("01")}'>{{cells["01"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("02")' :class='{cell: true, noteCell: isNoteCell("02"), tonicCell: isTonicCell("02")}'>{{cells["02"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("03")' :class='{cell: true, noteCell: isNoteCell("03"), tonicCell: isTonicCell("03")}'>{{cells["03"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("04")' :class='{cell: true, noteCell: isNoteCell("04"), tonicCell: isTonicCell("04")}'>{{cells["04"]}}</button></div>
        
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("10")' :class='{cell: true, noteCell: isNoteCell("10"), tonicCell: isTonicCell("10")}'>{{cells["10"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("11")' :class='{cell: true, noteCell: isNoteCell("11"), tonicCell: isTonicCell("11")}'>{{cells["11"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("12")' :class='{cell: true, noteCell: isNoteCell("12"), tonicCell: isTonicCell("12")}'>{{cells["12"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("13")' :class='{cell: true, noteCell: isNoteCell("13"), tonicCell: isTonicCell("13")}'>{{cells["13"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("14")' :class='{cell: true, noteCell: isNoteCell("14"), tonicCell: isTonicCell("14")}'>{{cells["14"]}}</button></div>

        <div class="string-cell"><hr class="string"><button @click='changeToTonic("20")' :class='{cell: true, noteCell: isNoteCell("20"), tonicCell: isTonicCell("20")}'>{{cells["20"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("21")' :class='{cell: true, noteCell: isNoteCell("21"), tonicCell: isTonicCell("21")}'>{{cells["21"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("22")' :class='{cell: true, noteCell: isNoteCell("22"), tonicCell: isTonicCell("22")}'>{{cells["22"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("23")' :class='{cell: true, noteCell: isNoteCell("23"), tonicCell: isTonicCell("23")}'>{{cells["23"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("24")' :class='{cell: true, noteCell: isNoteCell("24"), tonicCell: isTonicCell("24")}'>{{cells["24"]}}</button></div>

        <div class="string-cell"><hr class="string"><button @click='changeToTonic("30")' :class='{cell: true, noteCell: isNoteCell("30"), tonicCell: isTonicCell("30")}'>{{cells["30"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("31")' :class='{cell: true, noteCell: isNoteCell("31"), tonicCell: isTonicCell("31")}'>{{cells["31"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("32")' :class='{cell: true, noteCell: isNoteCell("32"), tonicCell: isTonicCell("32")}'>{{cells["32"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("33")' :class='{cell: true, noteCell: isNoteCell("33"), tonicCell: isTonicCell("33")}'>{{cells["33"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("34")' :class='{cell: true, noteCell: isNoteCell("34"), tonicCell: isTonicCell("34")}'>{{cells["34"]}}</button></div>

        <div class="string-cell"><hr class="string"><button @click='changeToTonic("40")' :class='{cell: true, noteCell: isNoteCell("40"), tonicCell: isTonicCell("40")}'>{{cells["40"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("41")' :class='{cell: true, noteCell: isNoteCell("41"), tonicCell: isTonicCell("41")}'>{{cells["41"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("42")' :class='{cell: true, noteCell: isNoteCell("42"), tonicCell: isTonicCell("42")}'>{{cells["42"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("43")' :class='{cell: true, noteCell: isNoteCell("43"), tonicCell: isTonicCell("43")}'>{{cells["43"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("44")' :class='{cell: true, noteCell: isNoteCell("44"), tonicCell: isTonicCell("44")}'>{{cells["44"]}}</button></div>

        <div class="string-cell"><hr class="string"><button @click='changeToTonic("50")' :class='{cell: true, noteCell: isNoteCell("50"), tonicCell: isTonicCell("50")}'>{{cells["50"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("51")' :class='{cell: true, noteCell: isNoteCell("51"), tonicCell: isTonicCell("51")}'>{{cells["51"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("52")' :class='{cell: true, noteCell: isNoteCell("52"), tonicCell: isTonicCell("52")}'>{{cells["52"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("53")' :class='{cell: true, noteCell: isNoteCell("53"), tonicCell: isTonicCell("53")}'>{{cells["53"]}}</button></div>
        <div class="string-cell"><hr class="string"><button @click='changeToTonic("54")' :class='{cell: true, noteCell: isNoteCell("54"), tonicCell: isTonicCell("54")}'>{{cells["54"]}}</button></div>
      </div>
    </div>
  </div>
</template>

<script>
import {
  ref
} from 'vue';

export default {
  name: 'GuitarChord',
  props: {
    name: String,
    scale: Array
  },
  setup(props) {
    var cells = ref({
      "00": "", "01": "", "02": "", "03": "", "04": "",
      "10": "", "11": "", "12": "", "13": "", "14": "",
      "20": "", "21": "", "22": "", "23": "", "24": "",
      "30": "", "31": "", "32": "", "33": "", "34": "",
      "40": "", "41": "", "42": "", "43": "", "44": "",
      "50": "", "51": "", "52": "", "53": "", "54": ""
    });

    const drawScale = (firstCell) => {
      //go from current string and cell to first string
      var currentString = parseInt(firstCell[0]);
      var currentCell = parseInt(firstCell[1]);
      var currentIntervalIndex = 0;
      while(currentString >= 0) {
        while(currentCell <= 4) {
          if(currentIntervalIndex > 11)
            currentIntervalIndex = 0;

          if(props.scale[currentIntervalIndex]) {
            cells.value[""+currentString+currentCell] = props.scale[currentIntervalIndex];
          }

          currentIntervalIndex += 1;
          currentCell += 1;
        }

        currentCell = 0;
        currentString -= 1;
        
        //adjust for standard tuning
        if(currentString == 1) {
          currentIntervalIndex -= 1;
        }
      }

      //go from current string and cell to sixth string
      currentString = parseInt(firstCell[0]);
      currentCell = parseInt(firstCell[1]) - 1;
      currentIntervalIndex = 11;
      while(currentString <= 5) {

        while(currentCell >= 0) {
          if(currentIntervalIndex < 0)
            currentIntervalIndex = 11;

          if(props.scale[currentIntervalIndex]) {
            cells.value[""+currentString+currentCell] = props.scale[currentIntervalIndex];
          }

          currentIntervalIndex -= 1;
          currentCell -= 1;
        }

        currentCell = 4;
        currentString += 1;

        //adjust for standard tuning
        if(currentString == 2) {
          currentIntervalIndex += 1;
        }
      }
    };
    
    drawScale("50");

    const changeToTonic = (cell) => {
    cells.value = {
      "00": "", "01": "", "02": "", "03": "", "04": "",
      "10": "", "11": "", "12": "", "13": "", "14": "",
      "20": "", "21": "", "22": "", "23": "", "24": "",
      "30": "", "31": "", "32": "", "33": "", "34": "",
      "40": "", "41": "", "42": "", "43": "", "44": "",
      "50": "", "51": "", "52": "", "53": "", "54": ""
    };
      drawScale(cell);
    };

    const isNoteCell = (cell) => {
      return cells.value[cell] != "" && cells.value[cell] != "1";
    };

    const isTonicCell = (cell) => {
      return cells.value[cell] == "1";
    };

    return {
      cells,
      drawScale,
      changeToTonic,
      isNoteCell,
      isTonicCell
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.scale-name {
  text-align: center;
  font-weight: normal;
}

.scale {
  display: grid;
  grid-template-columns: repeat(1, 1fr);
  grid-template-rows: repeat(1, 1fr);
}

.frets {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: repeat(1, 1fr);
  grid-column: 1 / 1;
  grid-row: 1 / 1;
}
.fret {
  border-left: 6px solid #916627;
  border-right: 6px solid #916627;
  height: 100%;
}
.start-middle-fret {
  border-right: 6px solid #916627;
  height: 100%;
}
.end-middle-fret {
  border-left: 6px solid #916627;
  height: 100%;
}

.strings {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
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
  border-radius: 100%;
  padding-top: 3px;
  padding-bottom: 3px;
  padding-left: 6px;
  padding-right: 6px;
}

.tonicCell {
  background-color: #f26c51;
}
.noteCell {
  background-color: #5d5dad;
}
.cell {
  color: white;
  opacity: 0.95;
  margin-left: 22px;
  margin-right: 22px;
}
button {
  padding: 0;
  border: none;
  background: none;
}
</style>
