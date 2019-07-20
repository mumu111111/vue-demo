<template>
    <div class="cell" @click ="onClickCell">
      <template v-if="x">{{text}}</template>
      <template v-else="x"></template>
    </div>
</template>

<script>
export default {
  name: "app",
  props: ["n"],
  data() {
    return {
      x: false,
      text: ""
    };
  },
  methods: {
    onClickCell() {
      if (this.text !== "") {
        return;
      }
      this.x = true;
      this.text = this.n % 2 == 0 ? "X" : "O";
      this.$emit("click", this.text);
    }
  }
};
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
