<script setup>
import {ref, reactive} from 'vue';

const taskList = reactive([{
  name: "task1",
  isDone: false
}, {
  name: "task2",
  isDone: false
}])

const newTaskName = ref('');

const addTask = (name) => {
  taskList.push({
    name: name, 
    isDone: false
  })
} 
</script>

<template>
  <div>

    <h1>Task List</h1>

    <div v-for="task in taskList" :key="task.name">
      <input type="checkbox" :id="task.name" v-model="task.isDone" />
      <label :for="task.name">{{ task.name }}</label>
    </div>

    <h1>Add Task</h1>

    <input type="text" id="newTaskName" v-model="newTaskName" />
    <button @click="addTask(newTaskName)">Add task</button>

  </div>
</template>

<style scoped>
h1 {
  font-weight: 500;
  font-size: 2.6rem;
  position: relative;
  top: -10px;
}

h3 {
  font-size: 1.2rem;
}

.greetings h1,
.greetings h3 {
  text-align: center;
}

@media (min-width: 1024px) {

  .greetings h1,
  .greetings h3 {
    text-align: left;
  }
}
</style>
