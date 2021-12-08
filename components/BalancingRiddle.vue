<template>
  <div>
    <p class="italic">Answer with the first letter of each color and no spaces</p>
    <input v-model="answer" class="text-black"/>
  </div>
</template>

<script>
export default {
  data() {
    return { answer: '' };
  },
  watch: {
    answer() {
      this.$emit('response', this.answer.toLowerCase().trim() == 'br')
    },
  },
};
</script>
