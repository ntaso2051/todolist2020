<template>
  <div>
    <div>TodoList</div>
    <div v-for="task in tasks" :key="task.task">
      <div class="task">
        <div class="task">
          タスク: {{ task.task }} 期限: {{ task.deadLine }}
          <span v-if="task.isAchived">済</span>
          <button @click="task.isAchived++" v-if="!task.isAchived">達成</button>
        </div>
      </div>
    </div>
    <div>
      <label>
        タスク
        <input type="text" v-model="newTask" />
      </label>
      <label>
        期限
        <input type="text" v-model="newDeadLine" />
      </label>
      <button @click="addTask">追加</button>
    </div>
  </div>
</template>

<script>
export default {
  name: "TodoList",
  data() {
    return {
      tasks: []
    };
  },
  methods: {
    addTask() {
      this.tasks.push({
        task: this.newTask,
        deadLine: this.newDeadLine,
        isAchived: 0
      });
    },
    achiveTask() {
      this.tasks.isAchived += 1;
    }
  }
};
</script>

<style></style>
