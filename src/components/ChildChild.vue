<template>
  <div class="child">
    <p>子コンポ</p>
    <grand-child 
      :value="ownerFullName"
      @input-first-name="inputFirstName"
      @input-last-name="inputLastName"
    />
    <grand-child2 
      :value="ownerFullNameKana"
      @input-first-name-kana="inputFirstNameKana"
      @input-last-name-kana="inputLastNameKana"
    />
  </div>
</template>

<script>
import GrandChild from '@/components/GrandChild.vue'
import GrandChild2 from '@/components/GrandChild2.vue'

export default {
  name: 'ChildChild',

  components: {
    'grand-child': GrandChild,
    'grand-child2': GrandChild2
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
      },
      ownerFullNameKana: {
        firstNameKana: this.value.firstNameKana,
        lastNameKana: this.value.lastNameKana
      }
    }
  },

  methods: {
    inputFirstName(e) {
      this.$emit('input-first-name', e)
    },
    inputLastName(e) {
      this.$emit('input-last-name', e)
    },
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
.child {
  width: 600px;
  height: 600px;
  background-color: pink;
}
</style>