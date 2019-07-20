<template>
   <div class="wrapper">
      {{n}}
      <div class="row">
        <Cell @click="xx" :n= "n"/>
        <Cell @click="xx" :n= "n"/>
        <Cell @click="xx" :n= "n"/>
      </div>
      <div class="row">
        <Cell @click="xx" :n= "n"/>
        <Cell @click="xx" :n= "n"/>
        <Cell @click="xx" :n= "n"/>
      </div>
      <div class="row">
        <Cell @click="xx" :n= "n"/>
        <Cell @click="xx" :n= "n"/>
        <Cell @click="xx" :n= "n"/>
      </div>
   </div>
 
    
</template>

<script>
import Cell from './Cell'

export default {
  name: 'app',
  data(){
    return {
       x: false,
       n:　0
    }
  },
  methods: {
    xx(){
      console.log('某个cell被电击了')
      this.n += 1
    }
  },
  components: {
      Cell
  }
}
</script>

<style>
.wrapper{
  font-size: 60px;
}
.row{
  display: flex;
}
</style>
