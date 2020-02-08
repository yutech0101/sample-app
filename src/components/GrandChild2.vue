<template>
  <div class="grand-child2">
    <p>ひ孫コンポーネント</p>
    <input type="text" @input="inputText" :value="value" :placeholder="placeholder">
  </div>
</template>

<script>

export default {
  name: 'GrandChild2',

  props: {
    placeholder: {
      type: String
    },
    value: {
      type: String
    }
  },

  methods: {
    inputText(e) {
      this.$emit('my-input', e.target.value)
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