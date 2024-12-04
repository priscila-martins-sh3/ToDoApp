<script>
  import TodoList from '../components/TodoList.vue';
  
  export default {
    components: { TodoList },
    data() {
      return {
        completedTasks: JSON.parse(localStorage.getItem('completedTasks')) || [], 
      };
    },
  };
</script>
<template>
  <div class="flex flex-col itens-center mt-8">
    <h2 class="flex justify-center font-bold text-gray-800 mb-6">Tarefas Concluídas</h2>
    <todo-list v-bind:tasks="completedTasks" v-bind:showCompleteButton="false" />
  </div>
</template> 
  