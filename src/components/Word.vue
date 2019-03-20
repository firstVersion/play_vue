<template>
  <span><input type="button" :value="word.message" @click="$emit('hoge',word.message)"></span>
</template>

<script>
export default {
  name: 'app',
  props: {
    word: String
  }
}
</script>

<style scoped>

</style>
