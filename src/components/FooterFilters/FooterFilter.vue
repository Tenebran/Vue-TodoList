<template>
  <footer class="footer">
    <span class="todo-count">{{ count }} left</span>
    <ul class="filters">
      <li>
        <a href="#/" class="selected" @click="$emit('set-filter', 'all')">All</a>
      </li>
      <li>
        <a href="#/active" @click="$emit('set-filter', 'active')" >Active</a>
      </li>
      <li>
        <a href="#/completed" @click="$emit('set-filter', 'complited')">Completed</a>
      </li>
    </ul>
    <button class="clear-completed">Clear completed</button>
  </footer>
</template>

<script setup>
const props = defineProps(['count'])
</script>

<style lang="sass" scoped></style>
