<template>
	<div>
		<form @submit.prevent="addTodo">
			<input type="text" v-model="title" name="title" placeholder="Add Todo...">
			<input type="submit" value="Submit" class="btn">
		</form>
	</div>
</template>

<script>
//import uuid from 'uuid'; 

export default {
	name: 'AddTodo',
	data() {
		return {
			title: ''
		}
	},
	methods: {
		addTodo() {
			const newTodo = {
				title: this.title,
				completed: false
			} 
			//Send it up to parent
			this.$emit('add-todo', newTodo)
			this.title = '';
		}
	}
};

</script>




<style type="text/css" scoped>
form {
	display: flex;
}
input[type=text] {
	flex: 10;
	padding: 5px;
	outline: none;
}
input[type=submit] {
	flex: 2;
	outline: none;
}
</style>