<template>
  <!-- <Header :text="myText" :number="1" role="parent" @set-text="myText = $event"></Header>
  <Header :text="'rerwreeg'" :number="7"></Header> -->

  <!-- <h1>hello h1</h1> -->
  <section class="todoapp">
    <header class="header">
      <h1 @click="myText = 'myText'">todos</h1>
      <input class="new-todo" placeholder="What needs to be done?" autofocus />
    </header>
    <section class="main">
      <input id="toggle-all" class="toggle-all" type="checkbox" />
      <label for="toggle-all">Mark all as complete</label>
      <ul class="todo-list">
        <li class="todo" v-for="i in [1, 2, 3]" :key="i">
          <div class="view">
            <input class="toggle" type="checkbox" />
            <label>todo #{{ i }}</label>
            <button class="destroy"></button>
          </div>
          <input class="edit" type="text" />
        </li>
      </ul>
    </section>
    <footer class="footer">
      <span class="todo-count"></span>
      <ul class="filters">
        <li>
          <a href="#/" class="selected">All</a>
        </li>
        <li>
          <a href="#/active">Active</a>
        </li>
        <li>
          <a href="#/completed">Completed</a>
        </li>
      </ul>
      <button class="clear-completed">Clear completed</button>
    </footer>
  </section>
  <footer class="info">
    <p>Double-click to edit a todo</p>
    <p>Created by <a href="http://twitter.com/oscargodson">Oscar Godson</a></p>
    <p>Refactored by <a href="https://github.com/cburgmer">Christoph Burgmer</a></p>
    <p>Part of <a href="http://todomvc.com">TodoMVC</a></p>
  </footer>
</template>

<script setup>
// import { onBeforeMount, ref } from 'vue';
// import Header from './components/Header/Header.vue';
// onBeforeMount(() => console.log('hello'));

// const myText = ref('12342');
</script>
