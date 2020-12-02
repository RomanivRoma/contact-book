<template>
    <li>
        <form @submit.prevent="onSubmit">
            <input type="text" v-model="title" placeholder="Enter full name...">
            <button class="add" type="submit"></button>
        </form>
    </li>    
</template>

<script>
export default {
    data(){
        return{
            title: ''
        }
    },
    methods: {
        onSubmit(){
            console.log('Submit',this.id);
            if(this.title.trim()){
                const newContact = {
                    id: Date.now(),
                    title: this.title,
                }
                this.$emit('add', newContact)
                this.title = ''
            }
        }
    }
}
</script>

<style scoped>
    li{
        position: relative;
        height: 30px;
        width: 70%;
        border: 2px solid gray;
        margin: 0 auto;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }   
    li .add{
        right: 0;
    }
    .add{
        float: right;
        position: relative;
        font-size: 1.5rem ;
        color: white;
        width: 30px;
        height: 30px;
        border: none;
        background: rgb(80, 140, 250);
        border-radius: 50%;
        transition: all .6s ease-in-out;
    }
    .add:after{
        content: '+';
        position: absolute;
        left: 6.9px;
        top: -1px;
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
    input{
        width: 300px;
    }
</style>
