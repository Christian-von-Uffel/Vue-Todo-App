<template>
    <div v-for="todo in todos" v-if="todo.completed" class="flex w-full space-between gap-6 text-lg items-center border-b">
        <div class="h-8 w-8 m-2 rounded-full flex-shrink-0 bg-gray-400 hover:bg-gray-500 border border-gray-500 hover:border-gray-600 transition duration-150 cursor-pointer" v-on:click="toggleComplete">
        </div>
        <div v-else>
            marked complete
        </div>
        <div class="w-full text-gray-500 line-through">
            {{todo.title}}
        </div>
        <div v-on:click="removeTodo" class="text-gray-700 cursor-pointer p-1 px-2">✗</div>
    </div>
</template>