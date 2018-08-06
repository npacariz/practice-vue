<template>
  <div>
      <h1>Contact List</h1>
      <form @submit.prevent>
        <label>Name</label>
        <input type="text" v-model='newContact.name'>
        <br>
        <label>Email</label>
        <input type="email" v-model='newContact.email'>
        <br>
        <button @click='addContact'>Add Contact</button>
      </form>
      <table border="1">
        <thead>
          <th>Name</th>
          <th>Email</th>
          <th></th>
        </thead>
        <tbody>
          <tr v-for="(contact, index) in contacts" :key='index'>
            <td>
                {{ contact.name }}
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
  </div>
</template>

<script>
export default {
  name: 'ContactList',

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

    }
  }
}
</script>

<style>

table {
  margin: 0 auto;
}


</style>

