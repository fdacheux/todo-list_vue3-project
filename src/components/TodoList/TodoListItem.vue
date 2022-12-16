<script setup lang="ts">
  import Form from "./Form/FormItem.vue";
  import Results from "./Results/ResultsItem.vue";
</script>

<template>
  <div class="container">
    <h2 class="title display-5 text-center">Please, enter tasks</h2>
    <Form />
    <Results class="mt-4" />
  </div>
</template>

<style scoped>
  .title {
    font-weight: 700;
  }
</style>
