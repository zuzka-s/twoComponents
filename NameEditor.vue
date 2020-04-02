<template>
  <div style="border: 1px solid red;">
    <p>
      Jméno:
      <input v-model="firstName" />
    </p>
    <p>
      Příjmení:
      <input v-model="lastName" />
    </p>

  </div>
</template>

<script>
export default {
  name: 'NameEditor',
  data () {
    const [firstName = '', lastName = ''] = this.value.split(' ')
    return {
      firstName,
      lastName
    }
  },
  props: {
    value: {
      type: String,
      default: ''
    }
  },
  watch: {
    joinedName () {
      this.setFullName()
    },
    value () {
      const [firstName = '', lastName = ''] = this.value.split(' ')
      this.firstName = firstName
      this.lastName = lastName
    }
  },
  computed: {
    joinedName () {
      return [this.firstName, this.lastName]
        .filter((item) => item !== '')
        .join(' ')
    }
  }, 
  methods: {
    setFullName () {
      this.$emit('input', this.joinedName)
    }
  }
}
</script>

<style scoped>
</style>



