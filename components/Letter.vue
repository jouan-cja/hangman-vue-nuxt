<template>
  <button class="letter" :class="{disabled}" @click="$emit('handleClick', letter)">
    {{ letter }}
  </button>
</template>

<script>
export default {
  props: {
    letter: {
      type: String,
      default: ''
    },
    disabled: {
      type: Boolean,
      default: false
    }
  }
}
</script>

<style lang="scss">
  .letter {
    height: 45px;
    width: 45px;
    font: 30px "Century Gothic", Futura, sans-serif;
    background-color: #82c0cc;
    color: white;
    border-radius: 50%;
    font-weight: bold;
    margin: 5px;
    text-align: center;

    &:hover {
      background-color: #489fb5;
      cursor: pointer;
    }

    &.disabled {
      background-color: #16697a;
      pointer-events: none;
    }
  }
</style>
