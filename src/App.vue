<template>
  <div>
    <h1>Pengelola Tugas Sederhana</h1>
    <!-- Form untuk menambahkan tugas baru -->
    <form-task :tasks="tasks" @add-task="addTask"></form-task>
    <!-- Daftar tugas -->
    <task-list :tasks="tasks" @delete-task="deleteTask"></task-list>
  </div>
</template>

<script>
import FormTask from "./components/FormTask.vue";
import TaskList from "./components/ListTask.vue";

export default {
  components: {
    FormTask,
    TaskList,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(newTask) {
      this.tasks.push(newTask);
    },
    deleteTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>
