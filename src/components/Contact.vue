<template>
    <li>
        <span>
            <strong>{{contact.id}}).</strong>
            {{contact.fullName}}
        </span>
            <button class="remove" v-on:click="$emit('remove',contact.id)"></button>
    </li>

</template>

<script>
export default {
    props:{
        contact: {
            type: Object,
            required: true
        }
    }
}
</script>
<style scoped>
    li{
        display: flex;
        justify-content: space-between;
        width: 70%;
        border: 2px solid gray;
        margin: 0 auto;
        padding: .5rem 2rem;
        margin-bottom: 1rem;
    }
    .remove{
		background-image: -webkit-linear-gradient(top, #f4f1ee, #fff);
		background-image: linear-gradient(top, #f4f1ee, #fff);
		border-radius: 50%;
		box-shadow: 0px 8px 10px 0px rgba(0, 0, 0, .3), inset 0px 4px 1px 1px white, inset 0px -3px 1px 1px rgba(204,198,197,.5);
		height: 25px;
		position: relative;
		width: 25px;			
		-webkit-transition: all .1s linear;
		transition: all .1s linear;
        right: 0;
	}

	.remove:after{
		color:#e9e6e4;
		content: "✖";
		left: -5px;
		top: 4px;
		display: block;
		font-size: 12px;
		height: 12px;
		text-decoration: none;
		text-shadow: 0px -1px 1px #878484, 1px 1px 1px white;
		position: absolute;
		width: 30px;
    }
    .remove:hover{
		background-image: -webkit-linear-gradient(top, #fff, #f4f1ee);
		background-image: linear-gradient(top, #fff, #f4f1ee);
		color:#0088cc;
        
	}
    .remove:hover:after{
        color:#eb2f2f;
		text-shadow:0px 0px 6px #eb2f2f;
    }
</style>