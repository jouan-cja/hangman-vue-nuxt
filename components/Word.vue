<template>
  <button class="answer m-1" :class="{show}">
    {{ word }}
  </button>
</template>

<script>
export default {
  props: {
    word: {
      type: String,
      default: ''
    },
    show: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss">
  .answer {
    height: 50px;
    width: 45px;
    font: bold 30px "Century Gothic", Futura, sans-serif;
    pointer-events: none;
    background-color: #F7F7F2;
    color: #F7F7F2;

    &.show {
      color: #899878;
    }
  }
</style>
