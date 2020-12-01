<template>
    <div>
        <h2>Contact list:</h2>
        <ul class="contact_list">
           <Contact
           v-bind:key="contact"
           v-for="contact in contacts"
           v-bind:contact = "contact"
           v-on:remove="removeContact"
            />
        </ul>
        <button class="add" v-on:click="$emit('add',)"></button>
    </div>
</template>

<script>
import Contact from '@/components/Contact'
export default {
    props: ['contacts'],
    components: {
        Contact
    },
    methods:{
        removeContact(id){
            this.$emit('remove',id)
        }
    }
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
    .add{
        position: relative;
        font-size: 1.5rem ;
        color: white;
        width: 50px;
        height: 50px;
        border: none;
        background: rgb(80, 140, 250);
        border-radius: 50%;
        transition: all .6s ease-in-out;
    }
    .add:after{
        content: '+';
        position: absolute;
        left: 16.5px;
        top: 8px;
        transition: all .6s ease-in-out;
    }
    .add:hover{
        background:  rgb(53, 122, 250);
    }
    .add:hover:after{
        transform: rotate(360deg);
    }
    .add:focus{
        background:  rgb(0, 89, 255);
    }
</style>