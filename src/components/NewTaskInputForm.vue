<template>
    <form v-on:submit.prevent="$emit('add')" class="flex">
        <input 
            type="text" 
            v-model="input" 
            placeholder="add a task and press enter to save" 
            class="w-full text-lg px-3 my-2 rounded-sm border border-gray-300 hover:border"
        >
        <button class="visible md:hidden bg-gray-400 hover:bg-gray-500 rounded shadow hover:shadow-lg transition duration-150">
            Add Task
        </button>
    </form>
</template>

<script>

    export default {
        props: ['value'],
        computed: {
            input: {
                get() {
                    return this.value;
                },
                set(val) {
                    this.$emit('input', val);
                }
            }
        }
    }

</script>