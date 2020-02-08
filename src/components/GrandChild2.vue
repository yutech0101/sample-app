<template>
  <div class="grand-child2">
    <p>ひ孫コンポーネント</p>
    <input type="text" :value="value.value" @input="inputText" :placeholder="value.placeholder">
  </div>
</template>

<script>

export default {
  name: 'GrandChild2',

  props: {
    value: {
      type: Object
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
  width: 150px;
  height: 70px;
  background-color: rgb(236, 220, 126);
}
</style>