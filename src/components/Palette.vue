<template>
  <div id="palette">
    <Word v-for="w in messages" :key="w" :word="w" v-on:hoge="pushWord"></Word>
  </div>
</template>

<script>
import Word from './Word.vue'

export default {
  name: 'app',
  components: {
      Word
  },
  data: ()=>{return {
    messages: [
    {message:'私',key:1},
    {message:'は',key:2},
    {message:'お腹が',key:3},
    {message:'空いた',key:4}]
  };},
  methods: {
    pushWord(msg) {
      this.$emit('push',msg)
    }
  }
}
</script>

<style scoped>

</style>
