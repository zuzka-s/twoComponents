<template>
  <div style="border: 1px solid red;">
    <p>
          Adresa:
            <input type="text" v-model="value.adress">
    </p>
    <p>
      Město:
      <input v-model="value.city" />
    </p>
    <p>
      PSČ:
      <input v-model="value.zip" />
    </p>

    <AdressEditor v-model="value.adress" />

  </div>
</template>

<script>
import AdressEditor from './AdressEditor.vue'

export default {
   components: {
    AdressEditor
},
  name: 'DeliveryAddressEditor',
 data () {
    const city = this.value.city;
    const zip = this.value.zip
    return {
      city,
      zip
    }
  }, 
  props: {
    value: {
      type: Object
    }
  }
}
</script>

<style scoped>
</style>



