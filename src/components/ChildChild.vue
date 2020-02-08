<template>
  <div class="child">
    <p>子コンポーネント</p>
    <grand-child 
      :value="ownerFullName"
      @input-first-name="inputFirstName"
      @input-last-name="inputLastName"
    />
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
      type: Object
    }
  },

  data() {
    return {
      ownerFullName: {
        firstName: this.value.firstName,
        lastName: this.value.lastName
      }
    }
  },

  methods: {
    inputFirstName(e) {
      this.$emit('input-first-name', e)
    },
    inputLastName(e) {
      this.$emit('input-last-name', e)
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