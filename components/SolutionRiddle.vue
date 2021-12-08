<template>
  <div>
    <p class="italic">Answer with the number for each blank with no spaces</p>
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
      this.$emit('response', this.answer.toLowerCase().trim() == '0110')
    },
  },
};
</script>
