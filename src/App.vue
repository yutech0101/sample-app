<template>
  <div id="app">
    <p>親コンポーネント</p>
    {{ owner }}
    <child-child :value="owner" @input="inputText4"/>
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
      owner: '親から送ったownerデータの値'
    }
  },

  methods: {
    inputText4(e) {
      this.owner = e
    }
  }
}
</script>

<style>

</style>
