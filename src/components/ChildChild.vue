<template>
  <div class="child">
    <p>子コンポーネント</p>
    <grand-child />
  </div>
</template>

<script>
import GrandChild from '@/components/GrandChild.vue'

export default {
  name: 'ChildChild',

  components: {
    'grand-child': GrandChild
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