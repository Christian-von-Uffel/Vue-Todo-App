<template>
	<div>
		<div class="font-bold text-center text-3xl text-gray-700 mt-24 mb-12">
            Simple Tailwind Todo App
        </div>
        <div class="max-w-2xl mx-auto border px-2 py-1 rounded shadow bg-gray-100">
            <input type="text" v-on:submit.prevent="addTask" placeholder="type a todo and press enter to save" class="w-full text-lg border-b mb-2">
            
			<todo-items></todo-items>

        </div>
	</div>
</template>

<script>
import Items from './components/Items.vue';
import NewTaskInputForm from './components/NewTaskInputForm.vue';
import incompleteTasks from './components/incomplete-tasks.vue';
import completedTasks from './components/completed-tasks.vue';

export default {
  	name: "app",
	components: {
		'new-task-input-form': NewTaskInputForm,
		'incomplete-tasks': incompleteTasks,
		'completed-tasks': completedTasks,
		'todo-items': Items,
	}
};
</script>
