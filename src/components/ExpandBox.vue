<script setup>
import { computed, ref, defineProps } from 'vue';

const props = defineProps(['title'])

const showContent = ref(false);
const buttonText = computed(() => 
  showContent.value ? 'Esconder' : 'Mostrar'
)

</script>

<template>
  <div>
    <button @click="showContent!=showContent">{{ buttonText }}</button>
    <div v-if="showContent" class="expand-box"  >
      <h1>{{ props.title }}</h1>
      <p>Conteúdo da caixa de expansão</p>
    </div>
  </div> 
</template>