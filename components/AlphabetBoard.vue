<template>
  <div class="alphabet-board">
    <Letter
      v-for="(status, letter) in alphabet"
      :key="letter"
      :letter="letter"
      :disabled="status"
      @handleClick="disableClick"
    />
  </div>
</template>

<script>
export default {
  props: {
    alphabet: {
      type: Object,
      default: () => {}
    }
  },
  methods: {
    disableClick (letter) {
      this.alphabet.[letter] = true
    }
  }
}
</script>

<style lang="scss">
  .alphabet-board {
    font: 20px "Century Gothic", Futura, sans-serif;
    padding: 30px;
    border: 1px dashed #999;
    border-radius: 5px;
    width: 500px;
  }
</style>
