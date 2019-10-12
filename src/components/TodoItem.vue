<template>
	<div v-bind:class="{'is-complete':todo.completed}" class="todo-item">
		<p>
			<input type="checkbox" v-on:change="markComplete">
			{{todo.title}}
			<button @click="$emit('del-todo', todo.id)" class="del">X</button>
		</p>
	</div>
</template>	

<script>
export default {
	name: 'TodoItem',
	props: ["todo"],
	methods: {
		markComplete() {
			this.todo.completed = !this.todo.completed;
		}
	}
};
</script>


<style>
.todo-item {
	background: #f4f4f4;
	padding: 10px;
	border-bottom: 1px #ccc dashed;
}
.is-complete {
	text-decoration: line-through;
	outline: none;
}
.del {
	background: #ff0000;
	color: #fff;
	border: none;
	padding: 5px 9px;
	border-radius: 50%;
	cursor: pointer;
	float: right;
	outline: none;
}

</style>