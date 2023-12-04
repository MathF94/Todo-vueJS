<template>
    <form action="" method="POST" @submit.prevent="Edit">
        <label for="task">Ma tâche
            <input type="text" name="task" id="task" placeholder='Modifier votre tâche' v-model="task.name">
        </label>
        <button class="btn">Valider</button>
    </form>
</template>

<script>
export default {
    name: 'EditComponent',
    props: {
        editTask: String,
        selectIndex: Number,
        isEditing: Boolean,
        tasks: Array
    },
    data() {
        return {
            task: this.editTask,
            tasksCopy: this.tasks,
            isEditingCopy: this.isEditing,
            selectIndexCopy: this.selectIndex
        }
    },

    methods: {
        Edit() {
            this.task = null,
            this.isEditingCopy = true
            this.selectIndexCopy = null

            this.tasksCopy.splice(this.selectIndexCopy, 1, {name: this.task, status: "to-do"})

            this.$emit('updateItems', this.isEditingCopy, this.selectIndexCopy)
        }
    },
}
</script>

<style scoped>

</style>