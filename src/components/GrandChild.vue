<template>
  <div class="grand-child">
    <p>孫コンポーネント</p>
    <grand-child2 />
  </div>
</template>

<script>
import GrandChild2 from '@/components/GrandChild2.vue'

export default {
  name: 'GrandChild',

  components: {
    'grand-child2': GrandChild2
  }
}
</script>

<style scoped>
.grand-child {
  width: 400px;
  height: 400px;
  background-color: rgb(0, 225, 255);
}
</style>