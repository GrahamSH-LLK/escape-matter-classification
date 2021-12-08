<template>
  <div>
    <p class="italic">Answer with the number of each answer and no spaces</p>
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
      this.$emit('response', this.answer.toLowerCase().trim() == '12215634')
    },
  },
};
</script>
