<template>
	<div>
		<div class="font-bold text-center text-3xl text-gray-700 mt-24 mb-12">
            Simple Vue/Tailwind Todo App
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
			todosList: []
		}
	},
	methods: {
		addTodo() {
			const newTodo = { title: this.newTodo, completed: false };
			this.todosList.push(newTodo);

			localStorage.setItem('todos', JSON.stringify(this.todosList));
		},
		removeTodo(id) {
			this.todosList.splice(id, 1);

			localStorage.setItem('todos', JSON.stringify(this.todosList));
		}
	},
	components: {
		'new-task-input-form': NewTaskInputForm,
		'todo-items': Items,
	},
	created() {
		const storageTodos = JSON.parse(localStorage.getItem('todos'));

		if(storageTodos) {
			this.todosList = storageTodos;
		}
	}
};
</script>
