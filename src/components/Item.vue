<template>
        <div>
            <div class="h-8 w-8 m-2 rounded-full flex-shrink-0 bg-gray-400 hover:bg-gray-500 border border-gray-500 hover:border-gray-600 transition duration-150 cursor-pointer" v-on:click="toggleComplete">
            </div>
            <div v-if="!todo.completed" class="w-full">
                {{todo.title}}
            </div>
            <div v-if="todo.completed" class="w-full text-gray-500 line-through">
                {{todo.title}}
            </div>
            <div v-on:click="removeTodo" class="text-gray-700 cursor-pointer p-1 px-2">✗</div>
        </div>
</template>

<script>

	export default {
		props: ['todo']
	}

</script>