<template>
  <div>
      <h1>Contact List</h1>

      <table border="1">
        <thead>
          <th>Name</th>
          <th>Email</th>
        </thead>
        <tbody>
          <tr v-for="(contact, index) in contacts" :key='index'>
            <td>
                {{ contact.name }}
            </td>
            <td>
                {{ contact.email }}
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
      ]
    }
  }
}
</script>

<style>

table {
  margin: 0 auto;
}


</style>

