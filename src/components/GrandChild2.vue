<template>
  <div class="grand-child">
    <p>孫２コンポ</p>
    <text-box :value="ownerFirstNameKana" @input="inputFirstNameKana"/>
    <text-box :value="ownerLastNameKana" @input="inputLastNameKana"/>
  </div>
</template>

<script>
import TextBox from '@/components/TextBox.vue'

export default {
  name: 'GrandChild２',

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
      ownerFirstNameKana: {
        value: this.value.firstNameKana,
        placeholder: 'ユウト'
      },
      ownerLastNameKana: {
        value: this.value.lastNameKana,
        placeholder: 'アラキ'
      }
    }
  },

  methods: {
    inputFirstNameKana(e) {
      this.$emit('input-first-name-kana', e)
    },
    inputLastNameKana(e) {
      this.$emit('input-last-name-kana', e)
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