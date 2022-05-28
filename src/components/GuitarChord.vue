<template>
  <div class="chord-container">
    <h4 class="chord-name">{{name}}</h4>
    <div class="chord">
      <div class="frets">
        <div class="fret"></div>
        <div class="empty-fret"></div>
        <div class="fret"></div>
      </div>
      <div class="strings">
        <div class="string-cell"><hr class="string"><div :class='getClassType("00")'>{{cells["00"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("01")'>{{cells["01"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("02")'>{{cells["02"]}}</div></div>
        
        <div class="string-cell"><hr class="string"><div :class='getClassType("10")'>{{cells["10"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("11")'>{{cells["11"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("12")'>{{cells["12"]}}</div></div>

        <div class="string-cell"><hr class="string"><div :class='getClassType("20")'>{{cells["20"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("21")'>{{cells["21"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("22")'>{{cells["22"]}}</div></div>

        <div class="string-cell"><hr class="string"><div :class='getClassType("30")'>{{cells["30"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("31")'>{{cells["31"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("32")'>{{cells["32"]}}</div></div>

        <div class="string-cell"><hr class="string"><div :class='getClassType("40")'>{{cells["40"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("41")'>{{cells["41"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("42")'>{{cells["42"]}}</div></div>

        <div class="string-cell"><hr class="string"><div :class='getClassType("50")'>{{cells["50"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("51")'>{{cells["51"]}}</div></div>
        <div class="string-cell"><hr class="string"><div :class='getClassType("52")'>{{cells["52"]}}</div></div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GuitarChord',
  props: {
    name: String,
    openStrings: Array,
    firstFinger: String,
    secondFinger: String,
    thirdFinger: String,
    fourthFinger: String,
    barre: Object,
    deadStrings: Array
  },
  setup(props) {
    var cells = {
      "00": "", "01": "", "02": "", 
      "10": "", "11": "", "12": "", 
      "20": "", "21": "", "22": "", 
      "30": "", "31": "", "32": "", 
      "40": "", "41": "", "42": "", 
      "50": "", "51": "", "52": ""
    };

    props.openStrings.forEach((openString) => {
      cells[openString+"0"] = "O";
    });

    props.deadStrings.forEach((deadString) => {
      cells[deadString+"0"] = "X";
    });

    cells[props.firstFinger] = "1";
    cells[props.secondFinger] = "2";
    cells[props.thirdFinger] = "3";
    cells[props.fourthFinger] = "4";

    props.barre.cells.forEach((cell) => {
      cells[cell+props.barre.position] = " ";
    });

    const getClassType = (cell) => {
      if(cells[cell] == "O")
        return "cell openStringCell";
      if(cells[cell] == "1" || cells[cell] == "2" || cells[cell] == "3" || cells[cell] == "4")
        return "cell fingeredCell";
      if(cells[cell] == " " && cell[0] == 0)
        return "cell barreCell barreCellStart";
      if(cells[cell] == " " && cell[0] == 5)
        return "cell barreCell barreCellEnd";
      if(cells[cell] == " ")
        return "cell barreCell";
      if(cells[cell] == "X")
        return "cell deadStringCell";
      return "cell";
    };

    return {
      cells,
      getClassType
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.chord-name {
  text-align: center;
  font-weight: normal;
}

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
  border-left: 6px solid #916627;
  border-right: 6px solid #916627;
  height: 100%;
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
  border-radius: 100%;
  padding-top: 3px;
  padding-bottom: 3px;
  padding-left: 6px;
  padding-right: 6px;
}

.fingeredCell {
  background-color: #f26c51;
}
.openStringCell {
  background-color: #7896c2;
}
.barreCellStart {
  border-radius: 10px 10px 0 0 !important;
}
.barreCellEnd {
  border-radius: 0 0 10px 10px !important;
}
.barreCell {
  padding: 0;
  border-radius: 0;
  border-left: 6px solid #f9684c !important;
  height: 100%;
}
.deadStringCell {
  background-color: grey;
}
.cell {
  color: white;
  opacity: 0.95;
}
</style>
