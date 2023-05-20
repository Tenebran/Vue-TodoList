<template>
  <header class="header">
    <h1 @click="myText = 'myText'">todos</h1>
    <input
      class="new-todo"
      placeholder="What needs to be done?"
      autofocus
      @keyup.enter="$emit('add-new-todo', $event.target.value)"
    />
  </header>
</template>

<script setup></script>

<style lang="sass" scoped></style>
