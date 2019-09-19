<template>
    <section>
        <h1>Todo list</h1>
         <form @submit.prevent="addTask" class="input-group">
                <div class="input-group-prepend">
                    <span class="input-group-text">Task</span>
                </div>
                <input type="text" ref="input" class="form-control">
                <button type="submit" class="btn btn-outline-primary">Add task</button>
        </form>
            <ul data-spy="scroll">
                <li v-for="(task, index) in tasks" :key="index" :class="[task.isTaskDone ? 'is-done': '']">
                    <a href="#" @click.prevent="openTodo(task.task)">{{time.getDate()}}.{{time.getMonth() + 1}}.{{time.getFullYear()}} {{time.getHours()}}:{{time.getMinutes()}} <br>
                     Task: {{task.task}}</a> 
                     <p>Done<input @input="task.isTaskDone = !task.isTaskDone" type="checkbox">
                     <button @click="deleteTask(task)" class="btn-danger btn-small">delete</button></p>
                </li>
            </ul>
    </section>
</template>

<script>
export default {
    data: () => ({
        tasks: [],
        time: new Date()
    }),
    methods: {
        openTodo(task) {
            this.$router.push('/todos/' + task);
        },
        addTask() {
            const text = this.$refs.input.value;
            this.tasks.push({task: text, isTaskDone: false});
            this.$refs.input.value = '';
            
        },
        deleteTask(task){
           const todoIndex = this.tasks.indexOf(task);
           this.tasks.splice(todoIndex,1);
        },
    }
}
</script>

<style>
.is-done {
 background-color: #5dff54;
}
</style>