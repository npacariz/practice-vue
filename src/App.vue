<template>
  <div id="app">
      <NavBar />
      <router-view></router-view>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import ContactList from './components/ContactList.vue'
import NavBar from './components/NavBar.vue'


export default {
  name: 'app',
  components: {
    HelloWorld,
    ContactList,
    NavBar
   
  },
  data() {
    return {
        parentTitle: 'Contact List Parent'

    }
  },
  methods: {
   
  }
 
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
 
}
</style>
