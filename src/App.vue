<template>
  <div id="app" class="container py-4">
    <b-container>
      <b-row class="justify-content-md-center">
        <b-col md="8">
          <h1 class="text-center">Daftar Tugas</h1>

          <!-- Input Section -->
          <TodoInput :onAddTask="addTask" />

          <!-- Task List -->
          <TodoList :tasks="tasks" :onRemoveTask="removeTask" />
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import TodoInput from './components/TodoInput.vue';
import TodoList from './components/TodoList.vue';

export default {
  components: {
    TodoInput,
    TodoList,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    addTask(task) {
      this.tasks.push({ text: task, completed: false });
    },
    removeTask(index) {
      this.tasks.splice(index, 1);
    },
  },
};
</script>

<style>
body {
  background-color: #f8f9fa;
}
</style>
