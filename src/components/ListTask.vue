<template>
  <ul v-if="tasks.length > 0">
    <li v-for="(task, index) in tasks" :key="index">
      {{ task.title }}
      <button @click.stop="deleteTask(index)">Hapus</button>
    </li>
  </ul>
  <p v-else>Tidak ada tugas yang perlu dikerjakan saat ini.</p>
</template>

<script>
export default {
  props: {
    tasks: {
      type: Array,
      default: () => [],
    },
  },
  methods: {
    deleteTask(index) {
      if (window.confirm("Apakah Anda yakin ingin menghapus tugas ini?")) {
        this.tasks.splice(index, 1);
      }
    },
  },
};
</script>
