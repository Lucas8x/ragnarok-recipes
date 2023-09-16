<script setup lang="ts">
import ListTitle from '../components/ListTitle.vue';
</script>

<template>
  <div
    class="flex h-[55vh] w-screen items-center justify-center bg-lime-500 text-white"
  >
    <div class="grid grid-cols-2 grid-rows-2 gap-x-52 gap-y-0">
      <div class="flex max-w-sm flex-col">
        <ListTitle icon="itens" title="Requerimentos" />

        <slot name="itens"></slot>
      </div>

      <div class="col-span-1 row-span-2 flex max-w-sm flex-col">
        <ListTitle icon="preparo" title="Modo de preparo" />
        <slot name="prepare"></slot>
      </div>

      <div class="flex max-w-sm flex-col">
        <ListTitle icon="skills" title="Pre-Requisitos" />
        <slot name="prerequisite"></slot>
      </div>
    </div>
  </div>
</template>
