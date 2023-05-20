<template>
  <li
    class="todo"
    :class="{
      'completed': props.todo.isComplited,
    }"
  >
    <div class="view">
      <input class="toggle" type="checkbox" @input="$emit('toggleState', props.todo.id)" 
      :checked="props.todo.isComplited"
      />
      <label>{{ props.todo.title }} </label>
      <button class="destroy"></button>
    </div>
    <input class="edit" type="text" />
  </li>
</template>
<script setup>
const props = defineProps(['todo']);
console.log(props.todo.isComplited);
</script>
<style></style>
