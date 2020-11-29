<template>
	<div>
		<div v-for="(todo,id) in todos" :key="id">

			<todo-item :todo="todo"></todo-item>

		</div>
	</div>

</template>

<script>
	import Item from './Item.vue';

    export default{
		components: {
			'todo-item': Item
		},
        data() {
            return {
				todos: [
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
        }
    }
</script>