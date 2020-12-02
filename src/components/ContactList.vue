<template>
    <div>
        <h2>Contact list:</h2>
        <ul class="contact_list">
           <Contact
                v-bind:key="contact"
                v-for="(contact, i) in contacts"
                v-bind:contact = "contact"
                v-bind:index="i"
                v-on:remove="removeContact"
            />
            <AddContact
                v-on:add="addContact"
             />
        </ul>

    </div>
</template>

<script>
import Contact from '@/components/Contact'
import AddContact from '@/components/AddContact'
export default {
    props: ['contacts'],
    components: {
        Contact,
        AddContact
    },
    methods:{
        removeContact(id){
            this.$emit('remove',id)
        },
        addContact(c){
            this.contacts.push(c)
        }
    },
    // computed:{
    //     filterContacts: function(){
    //         this.$emit('filter')
    //     }
    // }
}
</script>
<style scoped>
   
    h2{
        display: flex;
    }
    .contact_list{
        list-style: none;
        margin: 30px 0 ;
        padding: 0;
    }
    
</style>