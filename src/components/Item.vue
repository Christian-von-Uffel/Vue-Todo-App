<template>
        <div class="flex w-full space-between gap-4 text-lg items-center border-b">
            <div 
                class="h-8 w-8 m-2 rounded-full flex-shrink-0 bg-gray-400 hover:bg-gray-500 border border-gray-500 hover:border-gray-600 transition duration-150 cursor-pointer" 
                @click="toggleComplete"
            >
            </div>
            <div 
                class="w-full"
                :class="completedClasses"
            >
                {{todo.title}}
            </div>
            <div @click="$emit('remove')" class="text-gray-700 cursor-pointer p-1 px-2">X</div>
        </div>
</template>

<script>

	export default {
        props: ['todo'],
        computed: {
            completedClasses() {
                return this.todo.completed ? 'text-gray-500 line-through' : '';
            }
        },
        methods: {
            toggleComplete(){
                this.todo.completed = !this.todo.completed;
            }
        }
	}

</script>