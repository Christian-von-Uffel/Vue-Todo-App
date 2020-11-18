<template>

    <div v-for="(todo,id) in todos" :key="id" class="flex w-full space-between gap-4 text-lg items-center border-b">
         items
    </div>

</template>

<script>
    export default{
        data(){
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
</script>