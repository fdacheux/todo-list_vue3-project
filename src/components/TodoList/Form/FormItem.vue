<script setup lang="ts">
  import { reactive, ref } from "vue";
  import ResultItem from "./ResultItem.vue";
  const formData = ref({
    task: "",
  });
  const resultsArr: string[] = reactive([]);
  const addTask = (task: string) => {
    resultsArr.push(task);
    formData.value.task = "";
  };
  const deleteTask = (index: number) => {
    resultsArr.splice(index, 1);
  };
</script>

<template>
  <div class="container">
    <form>
      <div class="form-group">
        <label for="todo" class="mt-4 mb-2">Task </label>
        <input
          type="text"
          id="todo"
          class="form-control"
          v-model="formData.task"
        />
      </div>
      <button
        class="btn btn-primary mt-4"
        @click.prevent="addTask(formData.task)"
      >
        Create task
      </button>
    </form>
    <ul class="cards-group mt-4">
      <li class="card mt-2" :key="index" v-for="(task, index) in resultsArr">
        <ResultItem @removeTask="deleteTask" :id="index" :task="task" />
      </li>
    </ul>
  </div>
</template>

<style scoped src="./FormItem.css"></style>
