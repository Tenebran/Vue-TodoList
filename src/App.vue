<template>
  <!-- <Header :text="myText" :number="1" role="parent" @set-text="myText = $event"></Header>
  <Header :text="'rerwreeg'" :number="7"></Header> -->

  <!-- <h1>hello h1</h1> -->
  <section class="todoapp">
    <todo-header @add-new-todo="addTodo"></todo-header>
    <section class="main">
      <input id="toggle-all" class="toggle-all" type="checkbox" />
      <label for="toggle-all">Mark all as complete</label>
      <ul class="todo-list">
        <todo-item
          v-for="todo in todoList"
          :key="todo.id"
          :todo="todo"
          @toggle-state="toggleTodoState"
        ></todo-item>
      </ul>
    </section>
    <footer-filter :count="activeTodoCount" @set-filter="filter = $event"></footer-filter>
  </section>
  <Footer></Footer>
</template>

<script setup>
import Footer from './components/Footer/Footer.vue';
import TodoItem from './components/TodoList/TodoItem.vue';
import FooterFilter from './components/FooterFilters/FooterFilter.vue';
import TodoHeader from './components/TodoHeader/TodoHeader.vue';
import { v4 } from 'uuid';
import { computed, ref } from 'vue';
// import { onBeforeMount, ref } from 'vue';
// import Header from './components/Header/Header.vue';
// onBeforeMount(() => console.log('hello'));

// const myText = ref('12342');
const props = defineProps(['i']);
const todos = ref([
  { id: v4(), title: 'Buy Pc', isComplited: false },
  { id: v4(), title: 'Run', isComplited: true },
  { id: v4(), title: 'Clean', isComplited: false },
]);

function addTodo(text) {
  todos.value.push({ id: v4(), title: text, isComplited: false });
}

const activeTodoCount = computed(() => todos.value.filter(t => !t.isComplited).length)

function toggleTodoState(id) {
  const todo = getTodoById(id);
  todo.isComplited = !todo.isComplited;
}

const filter = ref('all')
function todosToShow(){
switch(filter.value){
  case 'all': return todos.value
  case 'active': return todos.value.filter(t => !t.isComplited)
  case 'complited': return todos.value.filter(t => t.isComplited)
}
}

const todoList = computed(todosToShow)

function getTodoById(id) {
  console.log(id);
  return todos.value.find(t => t.id === id);
}
</script>
