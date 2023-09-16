<script setup lang="ts">
defineProps<{
  icon: string;
  title: string;
}>();
</script>

<template>
  <div class="flex items-center">
    <img class="h-12 w-auto" :src="`${icon}.png`" alt="" />
    <p class="text-4xl font-medium">{{ title }}</p>
  </div>
</template>
