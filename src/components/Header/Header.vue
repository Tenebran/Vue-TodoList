<template>
  <div role="child">
    <h1 @click="setText">{{ myText }}</h1>
    <h4>{{ props.number }}</h4>
  </div>
</template>

<script setup>
import { computed, ref } from 'vue';

const props = defineProps(['text', 'number']);

const myText = computed(() => props.text + '!!!!');
const emit = defineEmits();

function setText() {
  emit('set-text', 'new text');
}
</script>

<style scoped>
h1 {
  color: blue;
}
</style>
