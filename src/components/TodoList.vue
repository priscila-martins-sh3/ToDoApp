<script>
import TodoItem from './TodoItem.vue'

export default {
    components: { TodoItem },
    props:  {
        tasks: Array,
        showCompleteButton: {type: Boolean, default: false,},
    },
  }
</script>

<template>
    <div>
      <todo-item
        v-for="task in tasks"
        v-bind:key="task.id"
        v-bind:task="task"
        v-bind:showCompleteButton="showCompleteButton"
        @mark-completed="$emit('mark-completed', task)"
      />
    </div>
</template>
  
  
  
 
 
  