<template>
  <div class="flex flex-wrap">
    <div class="w-1/2 p-4 cursor-pointer" @click="correct = false">
      Compound
    </div>
    <div class="w-1/2 p-4 cursor-pointer" @click="correct = true">Colloid</div>
    <div class="w-1/2 p-4 cursor-pointer" @click="correct = false">
      Solution
    </div>
    <div class="w-1/2 p-4 cursor-pointer" @click="correct = false">
      Heterogenous Mixture
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      correct: false,
    }
  },
  watch: {
    correct() {
        if (this.correct) return this.$emit('correct')
        return this.$emit('wrong')
    },
  },
}
</script>
