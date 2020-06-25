<template>
  <div v-quel="query">
    quel app
    <div>{{ count }}</div>
    <div>
      <button @click="count--">-</button>
      <button @click="count++">+</button>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  name: "App",
  data: (): {
    count: number;
    query: "CREATE" | "SELECT" | "INSERT" | "UPDATE" | "DELETE";
  } => ({
    count: 0,
    query: "SELECT"
  }),
  directives: {
    quel: function(el, bindings, vnode) {
      const { children } = el;
      const { value } = bindings;
      console.log(children, value);
    }
  }
};
</script>
