<template>
    <div class="flex flex-col itens-center mt-8">
      <todo-form @add-task="addTask" />      
      <h2 class="flex justify-center font-bold text-gray-800 mb-6">Tarefas Pendentes</h2>      
      <todo-list v-bind:tasks="tasks" v-bind:showCompleteButton="true" @mark-completed="markAsCompleted" />
    </div>
  </template>
  
  <script>
  import TodoForm from '../components/TodoForm.vue';
  import TodoList from '../components/TodoList.vue';
  
  export default {
    components: { TodoForm, TodoList },
    data() {
      return {
        tasks: JSON.parse(localStorage.getItem('tasks')) || [], 
      };
    },
    methods: {
      addTask(task) {
        this.tasks.push({ ...task, id: Date.now() }); 
        this.saveTasks();
      },
      markAsCompleted(task) {
        this.tasks = this.tasks.filter((t) => t.id !== task.id); // Remove a tarefa pendente
        const completed = JSON.parse(localStorage.getItem('completedTasks')) || [];
        completed.push(task);
        localStorage.setItem('completedTasks', JSON.stringify(completed));
        this.saveTasks();
      },
      saveTasks() {
        localStorage.setItem('tasks', JSON.stringify(this.tasks)); 
      },
    },
  };
  </script>
  
  
  
  