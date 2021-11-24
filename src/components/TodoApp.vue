<template>
  <div id="app">
    <div class="item">
      <h1 id="appTitle">{{ mainTitle }}</h1>
    </div>
    <div class="item">
      <input type="text" placeholder="todo" v-model="newItem" />
      <button @click="addItem">Add Todo</button>
    </div>

    <TodoItem
      v-for="item in items"
      v-bind:key="item.id"
      v-bind:item="item"
      @removeClicked="removeItem"
    />
  </div>
</template>

<script>
import TodoItem from "./TodoItem.vue";
export default {
  components: {
    TodoItem,
  },
  data() {
    return {
      mainTitle: "Hello Vue!",
      items: [
        { title: "Shopping", completed: false, id: 1 },
        { title: "Learn JavaScript", completed: false, id: 2 },
      ],
      newItem: "",
    };
  },
  methods: {
    addItem() {
      this.items.push({
        title: this.newItem,
        completed: false,
        id: Math.random(),
      });
      this.newItem = "";
    },
    removeItem(id) {
      const index = this.items.findIndex((el) => el.id === id);
      this.items[index].completed = true;
    },
  },
};
</script>

<style>
#appTitle {
  color: red;
  padding: 20px;
}
.item {
  display: flex;
  justify-content: center;
  align-items: center;
  max-width: 500px;
  padding-top: 20px;
  border: 1px solid #cdcdcd;
  margin: 0 auto;
  margin-bottom: 8px;
  padding: 10px;
  color: green;
}
#btnCompleted {
  margin-left: 10px;
}
.completed {
  opacity: 0.5;
}
.completed h2 {
  text-decoration: line-through;
}
</style>
