<template>
  <div id="app">
    <h1>Personal Contact Book</h1>   
    <hr>
    <input class="search" type="text" placeholder="Search contacts..."> 
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
          {id: 1, title: "Romaniv Roma Sergiyovich"},
          {id: 2, title: "Vodopyan Max Alexandrovich"},
          {id: 3, title: "Shevchnko Vlad Ihorovich"},
          {id: 4, title: "Shevchnko Vlad Ihorovich"},
          {id: 5, title: "Shevchnko Vlad Ihorovich"}
      ],
      // search: ''
    }
  },
  methods:{
    removeContact(id){
        this.contacts = this.contacts.filter(c => c.id !==id)
    }
  
  },
  // computed:{
  //   filterContacts: function(){
  //     this.contacts = this.contacts.filter((c) =>{
  //       return contact.fullName.match(this.search);
  //     })
  //   }
  // },
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
  border-radius: 0 5% 5% 0;
}
.search{
  margin-top: 20px;
}

</style>
