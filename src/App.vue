<template>
  <div id="app">
    <p>親コンポ</p>
    {{ owner }}
    <child-child
      :value="owner"
      @input-first-name="inputFirstName"
      @input-last-name="inputLastName"
      @input-first-name-kana="inputFirstNameKana"
      @input-last-name-kana="inputLastNameKana"
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
    },
    inputFirstNameKana(e) {
      this.owner.firstNameKana = e
    },
    inputLastNameKana(e) {
      this.owner.lastNameKana = e
    }
  }
}
</script>

<style>

</style>
