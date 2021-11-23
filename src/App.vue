<template>
  <div id="app">
    <h1>{{ mainTitle }}</h1>
    <div v-for="item in items" v-bind:key="item.id">
      <p>{{ item.title }}</p>
    </div>
    <button id="btn" @click="greet">Click me!</button>
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
    };
  },
  methods: {
    greet() {
      alert("Hello");
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
li {
  list-style: none;
  color: green;
}
</style>
