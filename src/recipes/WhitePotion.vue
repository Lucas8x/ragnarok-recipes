<script setup lang="ts">
import RecipeHeader from '../components/RecipeHeader.vue';
import RecipeInstructions from '../components/RecipeInstructions.vue';

import { ref } from 'vue';
const count = ref(200);

const MIN_AMOUNT = 200;
const STEP_AMOUNT = 200;

function decrement() {
  const newValue = count.value - STEP_AMOUNT;
  if (newValue < MIN_AMOUNT) {
    count.value = MIN_AMOUNT;
    return;
  }
  count.value = count.value - STEP_AMOUNT;
}

function increment() {
  count.value = count.value + STEP_AMOUNT;
}
</script>

<template>
  <div class="flex flex-col">
    <RecipeHeader
      class="bg-orange-500 text-white"
      :sprite="547"
      name="Poção Branca Compacta"
      :description="`Recupera cerca de 325 a 405 de HP.\n Peso: 5`"
      :value="count"
      :on-decrement="decrement"
      :on-increment="increment"
    />

    <RecipeInstructions>
      <template #itens>
        <ul class="ml-8">
          <li>{{ count }} Ervas Brancas</li>
          <li>{{ count }} Garrafas de Poção</li>
          <li>{{ count }} Vasilhas de Mistura</li>
        </ul>
      </template>

      <template #prerequisite>
        <ul class="ml-8">
          <li>Classe: Alquimista</li>
          <li>Habilidade: Preparar Poção Nv. 10</li>
          <li>1 Manual de Criação Vol 1: Poções Comuns</li>
          <li>Classe: Espiritualista</li>
          <li>Habilidade: Espírito do Alquimista</li>
        </ul>
      </template>

      <template #prepare>
        <ul class="ml-8 list-decimal">
          <li>
            Utilize a habilidade <b>Espírito do Alquimista</b> no seu personagem
          </li>
          <li>Utilize a habilidade <b>Criação Espiritual de Poções I</b></li>
        </ul>
      </template>
    </RecipeInstructions>
  </div>
</template>
