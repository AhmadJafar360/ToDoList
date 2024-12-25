<template>
  <b-list-group>
    <b-list-group-item v-for="(task, index) in tasks" :key="index" class="d-flex justify-content-between align-items-center">
      <div>
        <b-form-checkbox v-model="task.completed" class="me-2"></b-form-checkbox>
        <span :class="{ 'text-decoration-line-through text-muted': task.completed }">
          {{ task.text }}
        </span>
      </div>
      <b-button variant="danger" size="sm" @click="removeTask(index)">
        Delete
      </b-button>
    </b-list-group-item>
  </b-list-group>
</template>

<script>
export default {
  props: ['tasks', 'onRemoveTask'],
  methods: {
    removeTask(index) {
      this.onRemoveTask(index);
    },
  },
};
</script>
<style scoped>
</style>
