<template>
   <div class="wrapper">
      <div class="row">
        <Cell @click="xx(0, $event)" :n= "n"/>
        <Cell @click="xx(1, $event)" :n= "n"/>
        <Cell @click="xx(2, $event)" :n= "n"/>
      </div>
      <div class="row">
        <Cell @click="xx(3, $event)" :n= "n"/>
        <Cell @click="xx(4, $event)" :n= "n"/>
        <Cell @click="xx(5, $event)" :n= "n"/>
      </div>
      <div class="row">
        <Cell @click="xx(6, $event)" :n= "n"/>
        <Cell @click="xx(7, $event)" :n= "n"/>
        <Cell @click="xx(8, $event)" :n= "n"/>
      </div>
      <div>
        赢者为{{result}}
      </div>
   </div>
 
    
</template>

<script>
import Cell from "./Cell";

export default {
  name: "app",
  data() {
    return {
      x: false,
      n: 0,
      map: [[null, null, null], [null, null, null], [null, null, null]],
      result: ''
    };
  },
  methods: {
    xx(number, text) {
      console.log(`${number} 对应的内容是${text}`);
      this.map[Math.floor(number / 3)][number % 3] = text;
      this.n += 1;
      this.tell();
    },
    tell() {
      const map = this.map;
      for (var i = 0; i < 2; i++) {
        if (
          map[i][0] !== null &&
          map[i][0] === map[i][1] &&
          map[i][1] === map[i][2]
        ) {
          this.result = map[i][0];
        }
        for (var j = 0; j < 2; j++) {
          if (
            map[0][j] !== null &&
            map[0][j] === map[1][j] &&
            map[1][j] === map[2][j]
          ) {
            this.result = map[0][j];
          }
        }
        if (
          map[0][0] !== null &&
          map[0][0] === map[1][1] &&
          map[1][1] === map[2][2]
        ) {
          this.result = map[0][0];
        }
        if (
          map[0][2] !== null &&
          map[0][2] === map[1][1] &&
          map[1][1] === map[2][0]
        ) {
          this.result = map[0][2];
        }
      }
    }
  },

  components: {
    Cell
  }
};
</script>

<style>
.wrapper {
  font-size: 60px;
}
.row {
  display: flex;
}
</style>
