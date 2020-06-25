<template>
  <div v-quel="query">quel app
    <div>{{ count }}
    <div>
      <button @click="count--">-</button>
      <button @click="count++">+</button>
    </div>
  </div>
</template>

<script lang="ts">
type statement = "SELECT" | "INSERT" | "UPDATE" | "DELETE";

export default {
  name: "App",
  data: () => ({
    count: 0,
    query: "SELECT"
  }),
  directives: {
    quel: function(el, bindings, vnode) {
      const {children} = el
      const { value } = bindings;
      console.log(children, value);
    }
  }
};
</script>
