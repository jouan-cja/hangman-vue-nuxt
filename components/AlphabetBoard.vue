<template>
  <b-row class="justify-content-center">
    <b-col cols="12" md="5" class="alphabet-board">
      <Letter
        v-for="(status, letter) in alphabet"
        :key="letter"
        :letter="letter"
        :disabled="status"
        @handleClick="disableclick"
      />
    </b-col>
  </b-row>
</template>

<script>
export default {
  props: {
    alphabet: {
      type: Object,
      default: () => {}
    },
    disableclick: {
      type: Function,
      default: () => {}
    }
  }
}
</script>

<style lang="scss">
  .alphabet-board {
    border: 1px dashed #999;
    border-radius: 5px;
  }
</style>
