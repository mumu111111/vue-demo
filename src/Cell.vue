<template>
    <div class="cell" @click ="onClickCell">
      <template v-if="x">{{text}}</template>
      <template v-else="x"></template>
    </div>
</template>

<script>


export default {
  name: 'app',
  props: ['n'],
  data(){
    return {
       x: false,
       text: "",
    
    }
  },
  methods: {
      onClickCell(){
          this.x = true
          this.$emit('click')
          this.text = this.n%2 ==0 ? 'X' : 'O'
}
  }
}
</script>

<style>
.cell {
  border: 1px solid #000;
  width: 100px;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;

}
</style>
