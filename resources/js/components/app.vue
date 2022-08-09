<template>
    <div
        class="relative flex items-top justify-center min-h-screen bg-gray-100 dark:bg-gray-900 sm:items-center py-4 sm:pt-0">
        <div class="max-w-6xl mx-auto sm:px-6 lg:px-8 border p-3">
            <div class="flex justify-center pt-8 sm:justify-start sm:pt-0">
                Todo
            </div>

            <TaskItem @add-task="addTask" />

            <div class="input-group mb-3">
                <div class="input-group-text">
                    <input class="form-check-input mt-0" type="checkbox" value=""
                        aria-label="Checkbox for following text input">
                </div>
                <input type="text" class="form-control" aria-label="Text input with checkbox">
                <div class="input-group-text bg-info text-light">
                    <i class="bi bi-pencil-square"></i>
                </div>
                <div class="input-group-text bg-danger">
                    <i class="bi bi-trash-fill"></i>
                </div>
            </div>

        </div>
    </div>
</template>

<script>
import TaskUtil from "./TaskUtil.vue"
export default {
    name: "app",
    components: {
        TaskUtil
    },
    data() {
        return { tasks: [] }
    },
    methods: {
        addTask(text) {
            const newTask = { id: tasks.length + 1, text, isDone: false }
            this.tasks.push(newTask)
        },
        deleteTask(id) {
            this.tasks.filter(task => task.id !== id)
        },
        toggleTask(id) {
            const taskIdx = this.tasks.findIndex(task => task.id === id)
            if (taskIdx === -1)
                throw new Error("Task not found")
            this.tasks[taskIdx].isDone = !this.tasks[taskIdx].isDone
        },
    }
}
</script>

<style>
</style>
