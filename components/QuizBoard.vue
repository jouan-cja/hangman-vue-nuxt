<template>
  <div class="quiz-board">
    <client-only placeholder="Loading...">
      <Word
        v-for="(letter, key) in word"
        :key="key"
        :word="letter"
        :show="isLetterClicked(letter)"
      />
    </client-only>
  </div>
</template>

<script>
export default {
  props: {
    alphabet: {
      type: Object,
      default: () => {}
    },
    word: {
      type: String,
      default: ''
    }
  },
  methods: {
    isLetterClicked (letter) {
      return this.alphabet.[letter]
    }
  }
}
</script>

<style lang="scss">
  .quiz-board {
    font: 20px "Century Gothic", Futura, sans-serif;
    padding: 30px;
    text-align:center;
  }
</style>
