<template>
    <div class="task-item">
      <div class="d-flex justify-content-between align-items-center">
        <div class="d-flex align-items-center flex-grow-1">
          <div class="form-check">
            <input class="form-check-input" type="checkbox" :checked="isComplete" @change="toggleComplete" />
            <label class="form-check-label ml-2 flex-grow-1" :class="{ 'text-decoration-line-through': isComplete }">{{ name }}</label>
          </div>
          <div class="ms-3">
            <button class="btn btn-outline-danger" @click="deleteTask">Excluir</button>
          </div>
        </div>
      </div>
    </div>
  </template>
  
  
<script>
export default {
    name: 'TaskItem',
    props: {
        name: {
            type: String,
            required: true,
        },
        isComplete: {
            type: Boolean,
            default: false,
        },
    },
    methods: {
        toggleComplete() {
            this.$emit('toggle-complete');
        },
        deleteTask() {
            this.$emit('delete-task');
        },
    },
};
</script>
  