<template>
  <li
    class="todo"
    :class="{
      'completed': props.todo.isComplited,
      'editing': isEditing
    }"
  >
    <div class="view">
      <input class="toggle" type="checkbox" @input="$emit('toggleState', props.todo.id)" 
      :checked="props.todo.isComplited"
      />
      <label @dblclick="isEditing = true">{{ props.todo.title }} </label>
      <button class="destroy"></button>
    </div>
    <input class="edit" type="text" :value="props.todo.title"  @keydown.enter="stopEditing"/>
  </li>
</template>
<script setup>
import { ref } from 'vue';

const props = defineProps(['todo']);
const isEditing = ref(false)

const emit = defineEmits()
function stopEditing(event) {
  isEditing.value = false
  emit('change-title',  {id:  props.todo.id, newTitle: event.target.value} )
}
</script>
<style></style>
