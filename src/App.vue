<template>
  <div id="app">
    <p>親コンポーネント</p>
    {{ owner }}
    <child-child
      :value="owner"
      @input-first-name="inputFirstName"
      @input-last-name="inputLastName"
    />
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
        firstName: '',
        lastName: '',
        firstNameKana: '',
        lastNameKana: ''
      }
    }
  },

  methods: {
    inputFirstName(e) {
      this.owner.firstName = e
    },
    inputLastName(e) {
      this.owner.lastName = e
    }
  }
}
</script>

<style>

</style>
