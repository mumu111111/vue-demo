<template>
  <div id="app" @click ="x=true">
    <template v-if="x">X</template>
    <template v-else="x"></template>
  </div>
</template>

<script>


export default {
  name: 'app',
  data(){
    return {
       x: false
    }
  },
  components: {

  }
}
</script>

<style>
#app {
  border: 1px solid #000;
  width: 100px;
  height: 100px;
  display: flex;
  justify-content: center;
  align-items: center;

}
</style>
