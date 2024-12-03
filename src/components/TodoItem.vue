<script>
    export default {
        props: {
            task: Object,
            showCompleteButton: {type: Boolean, default: false,},
        },
    }
</script>
  
<template>
    <div 
        class="flex items-center justify-between bg-gray-100 p-4 rounded mt-6">
        <h3 
            class="text-lg font-medium">
            {{ task.title }}
        </h3>
        <button
            v-if="showCompleteButton" @click="$emit('mark-completed', task)"
            class="bg-green-500 text-white px-4 py-2 rounded"
        >
            Concluir
        </button>
    </div>
</template>
  