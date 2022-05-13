<template>
  <div class="chord">
    <div class="frets">
      <div class="first-second-fret fret"></div>
      <div class="empty-fret"></div>
      <div class="third-fourth-fret fret"></div>
    </div>
    <div class="strings">
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["00"])'>{{cells["00"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["01"])'>{{cells["01"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["02"])'>{{cells["02"]}}</div></div>
      
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["10"])'>{{cells["10"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["11"])'>{{cells["11"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["12"])'>{{cells["12"]}}</div></div>

      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["20"])'>{{cells["20"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["21"])'>{{cells["21"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["22"])'>{{cells["22"]}}</div></div>

      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["30"])'>{{cells["30"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["31"])'>{{cells["31"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["32"])'>{{cells["32"]}}</div></div>

      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["40"])'>{{cells["40"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["41"])'>{{cells["41"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["42"])'>{{cells["42"]}}</div></div>

      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["50"])'>{{cells["50"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["51"])'>{{cells["51"]}}</div></div>
      <div class="string-cell"><hr class="string"><div class="cell" :class='getClassType(cells["52"])'>{{cells["52"]}}</div></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'GuitarChord',
  props: {
    openString: String,
    firstFinger: String,
    secondFinger: String,
    thirdFinger: String,
    fourthFinger: String,
    barre: Object,
    deadString: String
  },
  setup(props) {
    var cells = {
      "01": "", "02": "", "03": "", 
      "11": "", "12": "", "13": "", 
      "21": "", "22": "", "23": "", 
      "31": "", "32": "", "33": "", 
      "41": "", "42": "", "43": "", 
      "51": "", "52": "", "53": ""
    };

    cells[props.openString+"0"] = "0";

    cells[props.deadString+"0"] = "X";

    cells[props.firstFinger] = "1";
    cells[props.secondFinger] = "2";
    cells[props.thirdFinger] = "3";
    cells[props.fourthFinger] = "4";

    props.barre.cells.forEach((cell) => {
      cells[cell+props.barre.position] = " ";
    });

    const getClassType = (string) => {
      if(string == "0")
        return "openStringCell";
      if(string == "1" || string == "2" || string == "3" || string == "4")
        return "fingeredCell";
      if(string == " ")
        return "barreCell";
      if(string == "X")
        return "deadStringCell";
      return "";
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

.fingeredCell {
  background-color: red;
  border-radius: 100%;
  padding: 5%;
  color: white;
}
.openStringCell {
  background-color: blue;
  border-radius: 100%;
  padding: 5%;
  color: white;
}
.barreCell {
  border-left: 6px solid yellow;
  height: 100%;
}
.deadStringCell {
  background-color: grey;
  border-radius: 100%;
  padding: 5%;
  color: white;
}
</style>
