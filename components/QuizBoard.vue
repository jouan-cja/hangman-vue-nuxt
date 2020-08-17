<template>
  <b-row class="justify-content-md-center p-3">
    <client-only placeholder="Loading...">
      <b-col cols="12" md="auto">
        <Word
          v-for="(letter, key) in word"
          :key="key"
          :word="letter"
          :show="isLetterClicked(letter)"
        />
      </b-col>
    </client-only>
  </b-row>
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
