<script setup lang="ts">
defineProps<{
  sprite: number;
  name: string;
  description: string;
  value: number;
  onDecrement: () => void;
  onIncrement: () => void;
}>();

import CircleButton from '../components/CircleButton.vue';
</script>

<template>
  <header class="flex h-[45vh] items-center justify-center gap-14">
    <img
      class="h-44 w-auto"
      :src="`recipes/${sprite}/${sprite}.png`"
      :alt="name"
    />

    <div class="flex flex-col gap-8">
      <div class="flex flex-col gap-6">
        <h1 class="text-6xl font-medium">{{ name }}</h1>
        <span class="whitespace-pre-line text-4xl">{{ description }}</span>
      </div>

      <div class="flex items-center gap-3">
        <span class="text-3xl">Quantidade</span>

        <div class="flex items-center gap-3">
          <CircleButton @click="onDecrement">
            <span class="text-2xl"> - </span>
          </CircleButton>

          <span class="text-3xl">{{ value }}</span>

          <CircleButton @click="onIncrement">
            <span class="text-2xl"> + </span></CircleButton
          >
        </div>
      </div>
    </div>
  </header>
</template>
