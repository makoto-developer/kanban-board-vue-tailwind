<template>
  <div id="app">
    <kanban-board />
  </div>
</template>
<script>
import KanbanBoard from "./components/KanbanBorad.vue";
export default {
  name: "App",
  components: {
    KanbanBoard
  },
};
</script>

