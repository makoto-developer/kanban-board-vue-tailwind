<template>
  <div class="flex justify-center">
    <div class="min-h-screen flex overflow-x-scroll py-12">
      <div
          v-for="column in columns"
          :key="column.title"
          class="bg-gray-100 rounded-lg px-3 py-3 column-width mr-3"
      >
        <p class="text-gray-700 font-semibold font-sans tracking-wide text-sm">{{ column.title }}</p>
        <draggable
            :list="column.tasks"
            :animation="200"
            :empty-insert-threshold="200"
            ghost-class="ghost-card"
            group="tasks"
        >
          <task-card
              v-for="(task) in column.tasks"
              :key="task.id"
              :task="task"
              class="mt-3 cursor-move"
          ></task-card>
        </draggable>
      </div>
    </div>
  </div>

</template>
<script>
import draggable from "vuedraggable";
import TaskCard from "./TaskCard.vue";
export default {
  components: {
    TaskCard,
    draggable
  },
  data() {
    return {
      columns: [
        {
          title: "Backlog",
          tasks: [
            {
              id: 1,
              title: "画像を大きくしてほしい",
              date: "2020/12/1",
              avatar: "https://pickaface.net/gallery/avatar/unr_laurine_220215_1851_3p375.png",
              type: "Frontend"
            },
            {
              id: 2,
              title: "webpack v5に移行する",
              avatar: "https://pickaface.net/gallery/avatar/unr_laurine_220215_1851_3p375.png",
              date: "2020/11/1"
            },
          ]
        },
        {
          title: "In Progress",
          tasks: [
            {
              id: 3,
              title: "vercelにデプロイする",
              date: "2020/10/1",
              avatar: "https://pickaface.net/gallery/avatar/unr_ines_220125_1209_10txeo.png",
            },
          ]
        },
        {
          title: "Review",
          tasks: []
        },
        {
          title: "Done",
          tasks: [
            {
              id: 4,
              title: "フロントエンドの基盤を用意する",
              avatar: "https://pickaface.net/gallery/avatar/20150331_002031_763_imamocineposl.png",
              date: "2020/8/31"
            },
          ]
        }
      ]
    };
  }
}
</script>
<style scoped>
.column-width {
  min-width: 320px;
  width: 320px;
}
.ghost-card {
  opacity: 0.5;
  background: #F7FAFC;
  border: 1px solid #4299e1;
}
</style>
