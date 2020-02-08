<template>
  <div class="grand-child">
    <p>孫コンポーネント</p>
    <grand-child2 :value="ownerFirstName" @input="inputFirstName"/>
    <grand-child2 :value="ownerLastName" @input="inputLastName"/>
  </div>
</template>

<script>
import GrandChild2 from '@/components/GrandChild2.vue'

export default {
  name: 'GrandChild',

  components: {
    'grand-child2': GrandChild2
  },

  props: {
    value: {
      type: Object
    }
  },

  data() {
    return {
      ownerFirstName: {
        value: this.value.firstName,
        placeholder: '裕登'
      },
      ownerLastName: {
        value: this.value.lastName,
        placeholder: '荒木'
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
.grand-child {
  width: 400px;
  height: 200px;
  background-color: rgb(0, 225, 255);
}
</style>