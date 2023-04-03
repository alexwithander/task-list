<template>
    <div class="container">
        <div  class="jumbotron jumbotron-fluid">
            <h2 class="display-4" >Minhas Tarefas</h2>
        </div>
        <ul class="list-group">
            <li v-for="(task, index) in tasks" :key="index" class="list-group-item">
                <TaskItem :name="task.name" :is-complete="task.isComplete" @toggle-complete="toggleComplete(index)"
                    @delete-task="deleteTask(index)" />
            </li>
        </ul>
        <div class="mt-3">
            <div class="input-group">
                <input type="text" class="form-control" v-model="newTask" />
                <button class="btn btn-outline-success" @click="addTask">Adicionar Tarefa</button>
            </div>
        </div>
    </div>
</template>
  
  
<script>
import TaskItem from './TaskItem.vue';

export default {
    name: 'TaskList',
    components: {
        TaskItem,
    },
    data() {
        return {
            tasks: [
                { name: 'Tarefa 1', isComplete: false },
                { name: 'Tarefa 2', isComplete: true },
                { name: 'Tarefa 3', isComplete: false },
            ],
            newTask: '',
        };
    },
    methods: {
        addTask() {
            if (this.newTask !== '') {
                this.tasks.push({ name: this.newTask, isComplete: false });
                this.newTask = '';
            }
        },
        toggleComplete(index) {
            this.tasks[index].isComplete = !this.tasks[index].isComplete;
        },
        deleteTask(index) {
            this.tasks.splice(index, 1);
        },
    },
};
</script>
  