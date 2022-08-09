<template>
    <div class="input-group mb-3">
        <input v-model="text" type="text" class="form-control" placeholder="Task name" aria-label="Task name"
            aria-describedby="button-addon2">
        <button @click="onAddTask" class="btn btn-success" type="button" id="button-addon2">Add Task</button>
    </div>
</template>

<script>
export default {
    name: "TaskUtil",
    data() {
        return { text: "" }
    },
    methods: {
        onAddTask() {
            this.$emit('addTask', this.text);
            this.text = ""
        }
    }

}
</script>

<style>
</style>
