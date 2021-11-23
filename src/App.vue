<template>
  <div id="app">
    <h1>{{ mainTitle }}</h1>
    <input type="text" placeholder="todo" v-model="newItem" />
    <div v-for="item in items" v-bind:key="item.id">
      <p class="item">{{ item.title }}</p>
    </div>
    <button id="btn" @click="addItem">Add Todo</button>
  </div>
</template>

<script>
export default {
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
  },
};
</script>

<style>
#app {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  padding-top: 20px;
  color: red;
}
#btn {
  margin-top: 35px;
}
.item {
  color: green;
}
</style>
