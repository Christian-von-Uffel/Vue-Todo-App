<template>
    <div>
        <div v-if="!todo.completed" class="text-lg cursor-pointer" v-on="toggleComplete">
            mark done button
        </div>
        <div v-else>
            marked complete
        </div>
        <div class="w-full">
            {{todo.title}}
        </div>
        <div class="cursor-pointer p-1">✗</div>
    </div>
</template>

<script>

	export default {
		props: ['todo']
	}

</script>