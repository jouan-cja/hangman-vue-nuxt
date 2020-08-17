<template>
  <button class="answer" :class="{show}">
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
    height: 60px;
    width: 60px;
    font-size: 30px;
    background-color: #F7F7F2;
    font-weight: bold;
    margin: 5px;
    text-align: center;
    pointer-events: none;
    color: #F7F7F2;

    &.show {
      color: #899878;
    }
  }
</style>
