<template>
    <b-input-group class="mb-3">
      <b-form-input
        v-model="task"
        placeholder="Tambahkan Tugas Baru"
        @keyup.enter="addTask"
      ></b-form-input>
      <b-input-group-append>
        <b-button variant="primary" @click="addTask">Add</b-button>
      </b-input-group-append>
    </b-input-group>
  </template>
  
  <script>
  export default {
    props: ['onAddTask'],
    data() {
      return {
        task: '',
      };
    },
    methods: {
      addTask() {
        if (this.task.trim() !== '') {
          this.onAddTask(this.task);
          this.task = '';
        }
      },
    },
  };
  </script>
  <style scoped>
  </style>
  