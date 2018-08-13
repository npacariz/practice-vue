<template>
  <div id='contacts'>
    <ContactListProps :contactList = 'contacts'/>

      <div class='contactDetalis' v-if="this.$route.params.id">
         <ContactDetalis  :contactList="contacts" @contactDeleted='deleteUser'/> 
      </div>
      
  </div>
</template>

<script>
import ContactListProps from '../components/ContactListProps.vue';
import ContactDetalis from '../components/ContactDetalis.vue';
import { contacts } from '../services/contacts'

export default {
  name:'Contacts',
  components: {
    ContactListProps, 
    ContactDetalis
    },
  data() {
    return {
    contacts: []
    
    }
    
  },

  beforeRouteEnter(to, from, next) {
      contacts.getAll()
      .then(response => {
          next( vm => {
            vm.contacts = response.data})
        })
       
  },

  computed: {
       contact() {
          let routePara = this.$route.params.id;
           return this.contacts.find((element) => element.id == routePara)
        }
    },
  methods: {
    deleteUser(id) {
        let index = this.contacts.findIndex(cont => cont.id === id)

       return this.contacts.splice(index, 1)
    }
  },

  
}
</script>

<style>
#contacts{
  max-width: 500px;
  margin: 0 auto;
}

.contactDetalis {
  margin-top: 40px;
}

</style>

