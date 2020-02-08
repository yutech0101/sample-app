<template>
  <div class="grand-child2">
    <p>ひ孫コンポーネント</p>
    {{ value }}
    <input type="text" :value="value" @input="inputText">
  </div>
</template>

<script>

export default {
  name: 'GrandChild2',

  props: {
    value: {
      type: String
    }
  },

  methods: {
    inputText(e) {
      this.$emit('input', e.target.value)
    }
  }
}
</script>

<style scoped>
.grand-child2 {
  width: 200px;
  height: 200px;
  background-color: rgb(236, 220, 126);
}
</style>