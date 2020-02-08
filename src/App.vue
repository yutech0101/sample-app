<template>
  <div id="app">
    <p>親コンポーネント</p>
    {{ owner }}
    <child-child />
  </div>
</template>

<script>
import ChildChild from './components/ChildChild.vue'

export default {
  name: 'App',

  components: {
    'child-child': ChildChild
  },

  data() {
    return {
      owner: ''
    }
  }
}
</script>

<style>

</style>
