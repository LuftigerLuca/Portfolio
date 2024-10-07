<script setup lang="ts">

import {computed, onMounted, ref} from "vue";

const props = defineProps({
  words: {
    type: Array,
    required: true
  }
})

const wordIndex = ref(0)
const letterIndex = ref(0)
const currentWord = computed(() => props.words[wordIndex.value])

//write 300ms, wait 1000ms, remove 150ms
onMounted(() => {
  write()
})


function write() {
  let interval = null

  interval = setInterval(() => {
    if (letterIndex.value >= currentWord.value.length) {
      clearInterval(interval)
      setTimeout(() => {
        erase()
      }, 1000)
      return
    }
    letterIndex.value++
  }, 300)
}

function erase() {
  let interval = null

  interval = setInterval(() => {
    if (letterIndex.value <= 0) {
      clearInterval(interval)
      if (wordIndex.value >= props.words.length - 1) {
        wordIndex.value = 0
      } else {
        wordIndex.value++
      }
      setTimeout(() => {
        write()
      }, 150)
      return
    }
    letterIndex.value--
  }, 150)
}
</script>

<template>
  <div>
    <span>{{ currentWord.slice(0, letterIndex) }}</span>
    <span style="color: transparent;">{{ currentWord.slice(letterIndex) }}</span>
  </div>
</template>

<style scoped>

</style>