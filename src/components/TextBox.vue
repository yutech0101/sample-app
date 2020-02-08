<template>
  <div class="text-box">
    <p>テキストコンポ</p>
    <input type="text" :value="value.value" @input="inputText" :placeholder="value.placeholder">
  </div>
</template>

<script>

export default {
  name: 'TextBox',

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
.text-box {
  width: 150px;
  height: 70px;
  background-color: rgb(236, 220, 126);
}
</style>