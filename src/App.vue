<template>
  <div id="app">
    <p>親コンポーネント</p>
    {{ owner }}
    <child-child :my-input3="inputText4"/>
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
      owner: {
        lastName: '',
        firstName: ''
      }
    }
  }
}
</script>

<style>

</style>
