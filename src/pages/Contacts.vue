<template>
  <div>
    <ContactListProps :contactList = 'contacts'/>

      <div v-if="this.$route.params.id">
         <ContactDetalis :contactList = 'contacts'/> 
      </div>
      
  </div>
</template>

<script>
import ContactListProps from '../components/ContactListProps.vue';
import ContactDetalis from '../components/ContactDetalis.vue';

export default {
  name:'Contacts',
  components: {
    ContactListProps, 
    ContactDetalis
    },
  data() {
    return {
    contacts: [
         { id: 1, name: 'John Doe', email: 'johndoe@example.com', number: '555-12345' },
         { id: 2, name: 'Pera Peric', email: 'peraperic@example.com', number: '555-54321' },
         { id: 3, name: 'Nenad Vujicic', email: 'nenad.v@example.com', number: '555-67890' }
       ]
    }
    
  }

 
}
</script>

<style>

</style>

