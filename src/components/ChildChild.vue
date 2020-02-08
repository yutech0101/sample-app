<template>
  <div class="child">
    <p>子コンポーネント</p>
    {{ value }}
    <grand-child :value="value" @input="inputText3"/>
  </div>
</template>

<script>
import GrandChild from '@/components/GrandChild.vue'

export default {
  name: 'ChildChild',

  components: {
    'grand-child': GrandChild
  },

  props: {
    value: {
      type: String
    }
  },

  methods: {
    inputText3(e) {
      this.$emit('input', e)
    }
  }
}
</script>

<style scoped>
.child {
  width: 600px;
  height: 600px;
  background-color: pink;
}
</style>