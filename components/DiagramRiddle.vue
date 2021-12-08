<template>
  <div>
    <p class="italic">Answer with the first letter of each shape and no spaces</p>
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
      this.$emit('response', this.answer.toLowerCase().trim() == 'tsc')
    },
  },
};
</script>
