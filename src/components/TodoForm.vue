<script>
    export default {
        name: "ToDoForm",
        data() {
            return {
                title: '',
            }
        },
        methods: {
            addTask() {
                if (this.title.trim()) {
                this.$emit('add-task',  {title: this.title}),
                this.title = ''            
                }
            },
        },
    }
</script>

<template>
    <div class="px-10">
        <form class="flex flex-col items-certer space-y-4" @submit.prevent="addTask">
        <input 
            v-model="title" type="text" placeholder="Nova tarefa"
            class="w-80 p-2 border border-gray-300 rounded mt-2"
            required
        />
        <button 
            type="submit"
            class="w-32 p-2 bg-blue-500 text-white rounded"
        >
            Adicionar
        </button>
    </form>
    </div>
   
</template>
  

  