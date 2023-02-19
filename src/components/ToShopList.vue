<script setup></script>

<template>
  <div class="container">
    <form action="">
      <input type="text" placeholder="Type your task" v-model="taskText" />
      <button @click.prevent="addTask" :disabled="!taskText">Add</button>
      <button
        class="delete-all" v-if="tasks.length > 1"
        @click.prevent="deleteAll"
      >
        Delete All
      </button>
    </form>

    <div class="tasks-list" v-for="(task, index) in tasks">
      <div
        class="task-box"
        @click="task.done = !task.done"
      >
        {{ task.words }}
      </div>
      <div class="delete" @click="deleteTask(index)">Delete</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tasks: [],
      taskText: "",
    };
  },

  methods: {
    addTask() {
      this.tasks.push({ words: this.taskText, done: false });
      this.taskText = "";
    },

    deleteTask(index) {
        this.tasks.splice(index, 1)
    },

    deleteAll() {
        this.tasks = []
    },
  },

};
</script>

<style scoped>
.container {
  text-align: center;
  margin-top: 10vh;
}

form {
  margin: 20px auto 10px;
  width: 500px;
  overflow: hidden;
}

input {
  background-color: #f7f7f7;
  border: 1px solid #eee;
  margin-bottom: 15px;
  width: calc(100% - 210px);
  height: 46px;
  padding: 10px;
  float: left;
}
.container form input:focus {
  outline: none;
}

button {
  width: 90px;
  height: 46px;
  padding: 10px;
  background-color: #197ac0e6;
  color: #ffffff;
  font-weight: 500;
  border-color: transparent;
  cursor: pointer;
  float: left;
  margin-left: 5px;
}
.container form button:disabled {
  opacity: 0.4;
  cursor: no-drop;
}
.container form button:focus {
  outline: none;
}

.delete-all {
  width: 110px;
  background-color: #dc0f00e8;
  font-weight: 500;
}

.tasks-list {
  width: 500px;
  margin: 0 auto;
}
.task-box {
  background-color: rgba(224, 224, 224, 0.906);
  padding: 15px;
  text-align: left;
  margin-bottom: 15px;
  margin-right: 5px;
  width: calc(100% - 86px);
  font-weight: 500;
  cursor: pointer;
  float: left;
  color: #000000;
}

.delete {
  float: right;
  width: 80px;
  background-color: #dc0f00e8;
  color: #fff;
  font-weight: 500;
  border-color: transparent;
  padding: 1px 10px;
  margin-top: 6px;
  cursor: pointer;
  height: 40px;
  line-height: 35px;
}
</style>
