<template>
  <div>
    <form @submit="addTodo">
      <input type="text" v-model="title" placeholder="Please enter todo here">
      <input type="submit" value="Submit" class="btn">
    </form>
  </div>
</template>

<script>
export default {
  name: "AddTodo",
  data() {
    return { title: "" };
  },
  methods: {
    addTodo(e) {
      e.preventDefault();
      const newTodo = {
        title: this.title,
        completed: false
      };
      // Send up to parent
      this.$emit("add-todo", newTodo);
      this.title = "";
    }
  }
};
</script>
<style scoped>
div {
    margin-left: 40px;
}

div input {
    padding: 2px 5px;
}

input[type="text"]{
    /* height: 15px; */
    width: 20%;
}
</style>

