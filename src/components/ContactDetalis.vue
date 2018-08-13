<template>
    <div>
      <h4>Contact Detalis</h4>
       <table class="table table-bordered">
        <thead>
          <tr>
            <th>First name</th>
            <th>Last name</th>
            <th>email</th>
            <th>number</th>
            <th></th>
            <th></th>
          </tr>
        </thead>
        <tbody>
      <tr>
         <td>{{contacts.first_name}}</td>
        <td>{{contacts.last_name}}</td>
        <td>{{contacts.email}}</td>
        <td> {{contacts.number}}</td>
        <td><button class='btn btn-danger' @click='deleteUser(contacts.id)'>Delete</button></td>
        <td><router-link :to="{name:'add-contact', params:{id: contacts.id}}"  class='btn btn-success'>Edit</router-link ></td>
      </tr>
      
    </tbody>
  </table>
     
    </div>
</template>

<script>
import { contacts } from '../services/contacts'
export default {
    props: ['contactList'],
    data() {
        return {
            
        }
    },
    methods: {
      deleteUser(id) {
        contacts.deleteContact(id)
        .then(()=> {
          this.$emit('contactDeleted', id )
          this.$router.push('/contacts')
        })
     
      }
    },
    computed: {
       contacts() {
        let routePara = this.$route.params.id;
        return this.contactList.find((element) => element.id == routePara)
      }
    }
}
</script>