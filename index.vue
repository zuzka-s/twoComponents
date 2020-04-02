<template>
    <div>
         <p>
         Jméno:
            <input type="text" v-model="deliveryAdress.name">
        Adresa:
            <input type="text" v-model="deliveryAdress.adress">
         Město:
            <input type="text" v-model="deliveryAdress.city">
        PSČ:
            <input type="text" v-model="deliveryAdress.zip">
    </p>
        <NameEditor v-model="deliveryAdress.name" />
         <AdressEditor v-model="deliveryAdress.adress" />
         <DeliveryAddressEditor v-model="deliveryAdress" />

    </div>
</template>

<script>
import NameEditor from './NameEditor'
import AdressEditor from './AdressEditor.vue'
import DeliveryAddressEditor from './DeliveryAddressEditor'

export default {
    components: {
    AdressEditor,
    NameEditor,
    DeliveryAddressEditor
    },
    data: function () {
    return {
      deliveryAdress: {
        name: 'John Doe',
        adress: 'U garáží 1611/1',
        city: 'Praha',
        zip: '17000'
      }
    }
}
}
</script>

<style>

</style>