<template>
  <li>
    <span v-bind:class="{ done: todo.сompleted }">
      <input type="checkbox" @change="todo.сompleted = !todo.сompleted" />
      <strong>{{ index + 1 }}</strong>
      {{ todo.title }}
    </span>
    <button class="delete" @click="$emit('remove-todo', todo.id)">
      &times;
    </button>
  </li>
</template>

<script>
export default {
  props: {
    todo: { type: Object, required: true },
    index: Number,
  },
  filters: {
    // uppercase(value) {
    //   return value.toUpperCase();
    // },
  },
};
</script>

<style scoped>
li {
  width: 800px;
  display: flex;
  justify-content: space-between;
  border: 1px solid rgb(83, 24, 83);
  margin: 15px;
  padding: 10px;
}
input {
  margin-right: 10px;
}
.delete {
  background-color: rgb(236, 86, 86);
  border: none;
  border-radius: 5px;
  font-weight: bold;
}
.done {
  text-decoration: line-through;
  color: red;
}
</style>
