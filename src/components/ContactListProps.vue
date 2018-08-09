<template>
    <div>
    
        <router-link v-for="(contact, index) in contactList" :key='index'
        :to="{name: 'contact-details', params: {id: contact.id}}" class="list-group-item" exact-active-class="active">
        
        {{contact.name}} 
        <br>
        </router-link >
        
     
    </div>
</template>

<script>
export default {
    props: ['contactList'],
    data() {
        return {

        }
    }
}
</script>

