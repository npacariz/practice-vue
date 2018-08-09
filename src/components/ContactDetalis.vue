<template>
    <div>
       <table class="table table-bordered">
    <thead>
      <tr>
        <th>id</th>
        <th>Name</th>
        <th>email</th>
        <th>number</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>{{contacts.id}}</td>
        <td>{{contacts.name}}</td>
        <td>{{contacts.email}}</td>
        <td> {{contacts.number}}</td>
      </tr>
      
    </tbody>
  </table>
     
    </div>
</template>

<script>
export default {
    props: ['contactList'],
    data() {
        return {
            
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