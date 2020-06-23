<template>
  <div v-quel>quel app</div>
</template>

<script lang="ts">
type statement = "SELECT" | "INSERT" | "UPDATE" | "DELETE";

export default {
  name: "App",
  data: () => ({
    el: null
  }),
  directives: {
    quel: function(el, binding, vnode) {
      console.log(el);
    }
  }
};
</script>
