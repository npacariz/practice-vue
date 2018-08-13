<template>
    <div id='listing'>
        <div  v-if="contactList.length">
            <router-link v-for="(contact, index) in contactList" :key='index'
            :to="{name: 'contact-details', params: {id: contact.id}}" 
            class="list-group-item" 
            exact-active-class="active">
            {{contact.first_name}}  {{contact.last_name}} 
            <br>
            </router-link >
        </div>
        <div v-else>
            <h3>No contacts in list</h3>
        </div>
    
     
    </div>
</template>

<script>
export default {
    props: ['contactList'],
    data() {
        return {

        }

    },
    
}
</script>

<style scoped>
</style>
