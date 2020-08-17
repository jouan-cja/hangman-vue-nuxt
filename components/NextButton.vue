<template>
  <button
    class="next-btn"
    @click="$emit('handleClick', words)"
  >
    Next
  </button>
</template>

<script>
export default {
  props: {
    words: {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style lang="scss">
.next-btn {
  margin-bottom: 20px;
  height: 25px;
  width: 100px;
  font-size: 15px;
  background-color: #ef959d;
  border-color: #ef959d;
  border-radius: 5%;
}
</style>
