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
type statement = "CREATE" | "SELECT" | "INSERT" | "UPDATE" | "DELETE";
let counterAppColumns = {};
export default {
  name: "App",
  data: (): {
    count: number;
    query: string;
  } => ({
    count: 0,
    query: `INSERT INTO counter_app { "fontFamily": "Gill Sans Extrabold, sans-serif", "display": "flex" }`
  }),
  directives: {
    quel: function(el, bindings, vnode) {
      let { children } = el;
      let { value } = bindings;
      let [statement0, statement1, tableName, ...styles] = value.split(" ");
      let stylesAsObject = JSON.parse(styles.join(""));
      console.log(stylesAsObject);
    }
  }
};
</script>
