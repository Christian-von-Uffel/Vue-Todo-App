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
	mounted(){
		if(localStorage.VueTodos){
			this.todosList = JSON.parse(localStorage.getItem("VueTodos"));
		}
	},
	watch:{
		todosList(){
			localStorage.setItem('VueTodos', JSON.stringify(this.todosList));
		}
	},
	methods: {
		addTodo() {
			const newTodo = { title: this.newTodo, completed: false };
			this.todosList.push(newTodo);
			this.newTodo = '';
		},
		removeTodo(id) {
			this.todosList.splice(id, 1);
		}
	},
	components: {
		'new-task-input-form': NewTaskInputForm,
		'todo-items': Items,
	},
};
</script>
