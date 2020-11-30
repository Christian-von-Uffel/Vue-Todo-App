<template>
	<div>
		<div v-for="(todo, id) in todos" :key="id">

			<todo-item  
				:todo="{...todo, id}" 
				@remove="$emit('remove', id)">
			</todo-item>

		</div>
	</div>

</template>

<script>
	import Item from './Item.vue';

    export default{
		props: ['todos'],
		computed: {
			completed() {
				// Return completed todos
			},
			incomplete() {
				// Return incomplete todos
			}
		},
		components: {
			'todo-item': Item
		},
    }
</script>