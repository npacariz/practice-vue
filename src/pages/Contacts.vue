<template>
  <div>
     <div class="container">
          <h2>Contacts</h2>  
  <table class="table">
    <thead>
      <tr>
        <th>id</th>
        <th>Name</th>
        <th>Email</th>
        <th>number</th>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(contact, index) in contacts" :key='index'>
        <td>{{contact.id}}</td>
        <td>{{contact.name}}</td>
        <td>{{contact.email}}</td>
        <td>{{contact.number}}</td>
       
      </tr>
    </tbody>
  </table>
</div>
  </div>
</template>

<script>
export default {
  name:'Contacts',
  
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

