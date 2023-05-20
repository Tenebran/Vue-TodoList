<template>
  <input
    class="new-todo"
    placeholder="What needs to be done?"
    autofocus
    @keyup.enter="$emit('add-new-todo', $event.target.value)"
  />
</template>

<script setup></script>

<style lang="sass" scoped></style>
