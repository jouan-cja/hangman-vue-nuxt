<template>
  <section class="container">
    <QuizBoard :word="word" :alphabet="alphabet" />
    <NextButton v-if="isFinished" :words="words" @handleClick="randomNewWord" />
    <AlphabetBoard :alphabet="alphabet" :disableclick="disableClick" />
  </section>
</template>

<script>
export default {
  data () {
    return {
      word: '',
      words: [
        'APPLE',
        'BANANA',
        'ORANGE',
        'AVOCADO',
        'BLACKBERRIES',
        'PEAR'
      ],
      alphabet: {
        A: false,
        B: false,
        C: false,
        D: false,
        E: false,
        F: false,
        G: false,
        H: false,
        I: false,
        J: false,
        K: false,
        L: false,
        M: false,
        N: false,
        O: false,
        P: false,
        Q: false,
        R: false,
        S: false,
        T: false,
        U: false,
        V: false,
        W: false,
        X: false,
        Y: false,
        Z: false
      }
    }
  },
  computed: {
    isFinished () {
      let finished = true
      const letters = this.word.split('')
      letters.forEach((letter) => {
        const show = this.alphabet.[letter]
        if (!show) { // if any correct letter not show up, keep playing
          finished = false
          return false
        }
      })

      return finished
    }
  },
  created () {
    this.randomNewWord(this.words)
  },
  methods: {
    getRandomInt (max) {
      return Math.floor(Math.random() * Math.floor(max))
    },
    randomNewWord (words) {
      const random = this.getRandomInt(words.length)
      this.word = words[random]
      this.alphabet = {
        A: false,
        B: false,
        C: false,
        D: false,
        E: false,
        F: false,
        G: false,
        H: false,
        I: false,
        J: false,
        K: false,
        L: false,
        M: false,
        N: false,
        O: false,
        P: false,
        Q: false,
        R: false,
        S: false,
        T: false,
        U: false,
        V: false,
        W: false,
        X: false,
        Y: false,
        Z: false
      }
    },
    disableClick (letter) {
      this.alphabet.[letter] = true
    }
  }
}
</script>

<style lang="scss">
  body {
    font: 20px "Helvetica", "Arial","LiHei Pro","黑體-繁","微軟正黑體", sans-serif;
    margin: 20px;
  }
  .container {
    margin: 0 auto;
    min-height: 100vh;
    justify-content: center;
    align-items: center;
    text-align: center;
    text-align: -webkit-center;
  }
</style>
