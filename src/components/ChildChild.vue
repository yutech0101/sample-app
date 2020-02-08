<template>
  <div class="child">
    <p>子コンポーネント</p>
    {{ owner }}
    <grand-child :value="owner" @input="owner = $event"/>
  </div>
</template>

<script>
import GrandChild from '@/components/GrandChild.vue'

export default {
  name: 'ChildChild',

  components: {
    'grand-child': GrandChild
  },

  data() {
    return {
      owner: '子から送ったownerの値'
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