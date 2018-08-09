<template>
  <div>
      <h1>{{title}}</h1>
      <form @submit.prevent>
        <label>Name </label>
        <input type="text" v-model='newContact.name'>
        <br>
        <br>
        <label>Email </label>
        <input type="email" v-model='newContact.email' >
       <br>
        <br>
        <button @click='addContact'>Add Contact</button>
        <br>
        <br>
      </form>
      <table border="1">
        <thead>
          <th>Name</th>
          <th>Email</th>
          <th></th>
        </thead>
        <tbody>
          <tr v-for="(contact, index) in contacts" :key='index'>
            <td v-if="contact.name != 'John'">
                {{ contact.name }}
            </td>
            <td v-else>
              Marko
            </td>
            <td>
                {{ contact.email }}
            </td>
            <td>
              <button @click='deleteContact(contact)'>Delete</button>
            </td>
          </tr>
        </tbody>
      </table>
      <button @click='callParent'>Call Parent</button>
  </div>
</template>

<script>
import ContactListProps from '../components/ContactListProps.vue';
export default {
  name: 'ContactList',
  props: ['title'],
  data() {
    return {
      contacts: [
        {name: "John", email: 'john@gmail.com'},
        {name: "Jack", email: 'jack@gmail.com'},
        {name: "Sussan", email: 'Sussan@gmail.com'},
        {name: "Jasmin", email: 'Jasmin@gmail.com'},
      ],

      newContact: {}
      
    }
  },
  methods: {
    addContact() {
      this.contacts.push(this.newContact)
      this.newContact = {}
    },
    deleteContact(contact) {

      let indexOfContactToDelete = this.contacts.indexOf(contact);

      this.contacts.splice(indexOfContactToDelete, 1);

    },
    callParent() {
      this.$emit('callFromChild', 'Test');
    }
  }
}
</script>

<style>

table {
  margin: 0 auto;
}


</style>

