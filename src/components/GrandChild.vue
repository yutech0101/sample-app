<template>
  <div class="grand-child">
    <p>孫コンポ</p>
    <text-box :value="ownerFirstName" @input="inputFirstName"/>
    <text-box :value="ownerLastName" @input="inputLastName"/>
  </div>
</template>

<script>
import TextBox from '@/components/TextBox.vue'

export default {
  name: 'GrandChild',

  components: {
    'text-box': TextBox
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