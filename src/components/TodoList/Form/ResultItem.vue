<script setup lang="ts">
  import { defineProps } from "vue";

  const props = defineProps({
    task: {
      type: String,
      required: true,
    },
    id: {
      type: Number,
      required: true,
    },
  });

  const emit = defineEmits(["removeTask"]);
</script>

<template>
  <p>{{ props.task }}</p>
  <button
    class="btn btn-danger btn-delete"
    @click="emit('removeTask', props.id)"
  >
    X
  </button>
</template>

<style scoped src="./FormItem.css"></style>
