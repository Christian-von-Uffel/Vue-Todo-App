<template>
	<div id="app">
		<div class="font-bold text-center text-3xl text-gray-700 mt-24 mb-12">
            Simple Tailwind Todo App
        </div>
        <div class="max-w-2xl mx-auto border px-2 py-1 rounded shadow bg-gray-100">
            <input type="text" v-on:submit.prevent="addTask" placeholder="type a todo and press enter to save" class="w-full text-lg border-b mb-2">
            
        </div>
	</div>
</template>

<script>
export default {
  	name: "app",
	data() {
		return {
			msg: "Welcome to Your Vue.js App",
		};
	},
};
</script>
