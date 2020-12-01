<template>
  <div id="app">
    <h1>Personal Contact Book</h1>   
    <hr>
    <input class="search" type="text" v-model="search" placeholder="Search"> 
    <ContactList
    v-bind:contacts="contacts"
    @remove="removeContact"
     />
  </div>
</template>

<script>
import ContactList from  '@/components/ContactList'
export default {
  name: 'App',
  data(){
    return {
      contacts: [
          {id: 1, fullName: "Romaniv Roma Sergiyovich"},
          {id: 2, fullName: "Vodopyan Max Alexandrovich"},
          {id: 3, fullName: "Shevchnko Vlad Ihorovich"},
          {id: 4, fullName: "Shevchnko Vlad Ihorovich"},
          {id: 5, fullName: "Shevchnko Vlad Ihorovich"}
      ]
    }
  },
  methods:{
    removeContact(id){
      this.contacts = this.contacts.filter(c => c.id !==id)
    }
  },
  components: {
    ContactList
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: wheat;
  width: 90%;
  margin: 0 auto;
  background: darkorchid;
  padding: 25px;
  border-radius: 5% 0;
}
.search{
  margin-top: 20px;
}

</style>
