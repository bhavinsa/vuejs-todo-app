<template>
  <div>
    <ul v-bind:key="todo.id" v-for="todo in todos">
      <li>
        <p v-bind:class="{'iscompleted': todo.completed}">
          <input type="checkbox" v-on:change="$emit('com-todo', todo.id)">
          {{todo.title}}
          <a href="#" @click="$emit('del-todo', todo.id)">Delete</a>
        </p>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  props: ["todos"]
};
</script>

<style>
div ul li {
  width: 45%;
  list-style-type: none;
  border-bottom: 0.5px solid black;
}

div ul li a {
  float: right;
}

.iscompleted {
  text-decoration: line-through;
}
</style>
