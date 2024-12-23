<template>
  <div class="container">
    <h1>Create a New Task</h1>
    <b-form @submit="onSubmit">
      <b-form-group label="Task Name" label-for="task-name-input">
        <b-form-input
          id="task-name-input"
          v-model="task.name"
          required
        ></b-form-input>
      </b-form-group>

      <b-form-group label="Task Description" label-for="task-desc-input">
        <b-form-textarea
          id="task-desc-input"
          v-model="task.description"
          required
        ></b-form-textarea>
      </b-form-group>

      <b-button type="submit" variant="primary">Create Task</b-button>
    </b-form>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';

export default defineComponent({
  name: 'TaskCreate',
  setup() {
    const task = ref({
      name: '',
      description: ''
    });

    const onSubmit = (event: Event) => {
      event.preventDefault();
      console.log('Task submitted:', task.value);
      // Add logic to handle task creation, e.g., send to an API
    };

    return {
      task,
      onSubmit
    };
  }
});
</script>

<style scoped>
/* Add any scoped CSS for your page here */
</style>
