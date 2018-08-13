<template>
  <div>
     <h1>{{title}}</h1>
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
          <button @click='onSubmit()' type="submit" class="btn btn-default">{{buttonTitle}}</button>
      </form>
  </div>
</template>

<script>
import { contacts } from '../services/contacts'
export default {

    data() {
      return {
        newContact: {},
        title: 'Add Contact',
        buttonTitle: 'Add'
      }
    },
    methods: {

      onSubmit() {
        this.$route.params.id ? this.edditContact() : this.addContact()
      },

      addContact() {
       contacts.postContact(this.newContact)
       .then(() => {
        this.$router.push('/contacts')})
       

       },
       edditContact() {
        contacts.edit(this.newContact)
       .then(() => {
        this.$router.push('/contacts')})
      

       }
    },
    created() {
      if(this.$route.params.id){
        this.title = 'Edit Contact'
        this.buttonTitle = 'Edit'
        contacts.get(this.$route.params.id)
        .then(response => this.newContact = response.data)
       
      }
    }
 



}
</script>

<style>

</style>
