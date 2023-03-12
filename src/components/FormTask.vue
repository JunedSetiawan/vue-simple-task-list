<template>
  <form @submit.prevent="addTask">
    <label for="task-title">Judul Tugas:</label>
    <input
      type="text"
      id="task-title"
      v-model="newTaskTitle"
      required
      placeholder="Tambah tugas baru"
    />
    <button type="submit">Tambah</button>
  </form>
</template>

<script>
export default {
  data() {
    return {
      tasks: [],
      newTaskTitle: "",
    };
  },
  methods: {
    addTask() {
      if (this.newTaskTitle) {
        const newTask = {
          title: this.newTaskTitle,
        };
        this.$emit("add-task", newTask);
        this.newTaskTitle = "";
      }
    },
  },
};
</script>
