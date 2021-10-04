<template>
  <div class="card" style="padding: 0px; border: 1px solid black">
    <h3>Your Tasks</h3>
  </div>

  <AddTask @add-task="updateTask" />
  <div class="srollable" style="max-height: 303px; overflow-y:scroll; margin-top: 14px;">
    <div class="card" :key="index" v-for="(task, index) in tasks">
      <h3>{{ task }}</h3>
    </div>

    <div v-if="tasks.length < 1">
      <div class="card" style="color: white; background-color: #f9dd18c7">
        <h2>No Tasks to show</h2>
      </div>
    </div>
  </div>
</template>

<script>
import AddTask from "./AddTask.vue";

export default {
  name: "Tasks",
  components: {
    AddTask,
  },
  data() {
    return {
      tasks: [],
    };
  },
  methods: {
    updateTask(task) {
      this.tasks.push(task);
    },
  },
};
</script>

<style>
.card {
  border: 2px dashed black;
  box-sizing: border-box;
  max-width: 80%;
  margin: 0 auto;
  margin-top: 18px;
  box-shadow: 3px 4px 6px rgba(43, 33, 33, 0.5);
}

.card:hover {
  box-shadow: 4px 3px 8px black;
}

</style>