<template>
  <div>
     <h1>Add-contacts</h1>
       <form class="form-inline" @submit.prevent>
          <br>
          <div class="form-group">
            <label for="pwd">First name:</label>
            <input type="text" class="form-control" v-model="newContact.first_name">
          </div>
             <br>
            <div class="form-group">
            <label for="pwd">Last name:</label>
            <input type="text" class="form-control" v-model="newContact.last_name">
          </div>
            <br>
           <div class="form-group">
            <label for="pwd">Email:</label>
            <input type="text" class="form-control" v-model="newContact.email">
          </div>
            <br>
           <div class="form-group">
            <label for="pwd">number:</label>
            <input type="tel" class="form-control" v-model="newContact.number">
          </div>
            <br>
          <button @click='onSubmit()' type="submit" class="btn btn-default">Add Contact</button>
      </form>
  </div>
</template>

<script>
import { contacts } from '../services/contacts'
export default {

    data() {
      return {

        newContact: {},
      }
    },
    methods: {

      onSubmit() {
        this.$route.params.id ? this.edditContact() : this.addContact()
      },

      addContact() {
       contacts.postContact(this.newContact)
       .then(response => {
        this.$router.push('/contacts')})
       .catch((err) => console.log(err))

       },
       edditContact() {
        contacts.edit(this.newContact)
       .then(response => {
        this.$router.push('/contacts')})
       .catch((err) => console.log(err))

       }
    },
    created() {
      if(this.$route.params.id){
        console.log(this.$route.params.id)
        contacts.get(this.$route.params.id).then(response => this.newContact = response.data).catch( erro => console.log(error))
      }
    }
 



}
</script>

<style>

</style>
