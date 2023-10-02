<script setup>
import {ref, reactive} from 'vue';
import Task from './Task.vue'

const taskStatusType = ["todo", "doing", "done"];

const taskList = reactive([{
  name: "task1",
  status: "todo"
}, {
  name: "task2",
  status: "todo"
}])

const newTaskName = ref('');

const addTask = (name) => {
  taskList.push({
    name: name, 
    status: "todo"
  })
} 
</script>

<template>
  <div>

    <h1>タスクリスト</h1>

    <div v-for="(task, index) in taskList" :key="task.name">
      <Task v-model="taskList[index]" :task-status-type="taskStatusType"></Task>
    </div>

    <h1>新規タスク追加</h1>

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
