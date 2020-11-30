<template>
	<div>
		<div class="font-bold text-center text-3xl text-gray-700 mt-24 mb-12">
            Simple Tailwind Todo App
        </div>
        <div class="max-w-2xl mx-auto border px-2 py-1 rounded shadow bg-gray-100">
            <new-task-input-form 
				v-model="newTodo"
				@add="addTodo" 
			/>
			<todo-items 
				:todos="todosList" 
				@remove="removeTodo" 
			/>
        </div>
	</div>
</template>

<script>
import NewTaskInputForm from './components/NewTaskInputForm.vue';
import Items from './components/Items.vue';

export default {
	name: "app",
	data() {
		return {
			newTodo: '',
			todosList: [
				{
					title: "clean apartment",
					completed: false
				},
				{
					title: "get groceries",
					completed: false
				},
				{
					title: "cook dinner",
					completed: false
				},
				{
					title: "set plates",
					completed: false
				},
				{
					title: "think of dinner ideas",
					completed: true
				},
			]
		}
	},
	methods: {
		addTodo() {
			this.todosList.push({ title: this.newTodo, completed: false });
		},
		removeTodo(id) {
			this.todosList.splice(id, 1);
		}
	},
	components: {
		'new-task-input-form': NewTaskInputForm,
		'todo-items': Items,
	}
};
</script>
