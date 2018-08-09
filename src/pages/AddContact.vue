<template>
  <div>
     <h1>Add-contacts</h1>
       <form class="form-inline" @submit.prevent>
          <div class="form-group">
            <label for="email">id:</label>
            <input type="text" class="form-control" v-model="newContact.id">
          </div>
          <br>
          <div class="form-group">
            <label for="pwd">Name:</label>
            <input type="text" class="form-control" v-model="newContact.name">
          </div>
            <br>
           <div class="form-group">
            <label for="pwd">Email:</label>
            <input type="text" class="form-control" v-model="newContact.email">
          </div>
            <br>
           <div class="form-group">
            <label for="pwd">number:</label>
            <input type="text" class="form-control" v-model="newContact.number">
          </div>
            <br>
          <button @click='addContact' type="submit" class="btn btn-default">Add Contact</button>
      </form>
  </div>
</template>

<script>
export default {

    data() {
      return {

        newContact: {},
      }
    },
    methods: {
      addContact() {
        this.$emit('addConcat', this.newContact)
    }
 
}


}
</script>

<style>

</style>
