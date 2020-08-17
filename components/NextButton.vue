<template>
  <b-row class="justify-content-center">
    <button
      class="next-btn"
      @click="$emit('handleClick', words)"
    >
      Next
    </button>
  </b-row>
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
  font: 15px "Helvetica", "Arial","LiHei Pro","黑體-繁","微軟正黑體", sans-serif;
  background-color: #ef959d;
  border-color: #ef959d;
  border-radius: 5%;
}
</style>
