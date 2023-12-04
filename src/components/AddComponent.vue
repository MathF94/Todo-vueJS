<template>
    <div class="formContainer">
        <!-- 4- -->
        <form action="" method="POST" @submit.prevent="submitTask">
            <label for="task">Ma tâche
                <input type="text" name="task" id="task" placeholder='Entrer votre nouvelle tâche' v-model="task" >
            </label>
            <button class="btn">Valider</button>
        </form>
    </div>
</template>

<script>
export default {
    name: 'AddComponent',
    props: {
        tasks: Array
    },
    data() {
        return {
            // 1-
            task: null,
            tasksCopy: this.tasks,
            selectIndex: null,
            isEditing: true,
        }
    },
    methods: {
        submitTask(){
            // si ma tâche est vide, elle ne peut pas être intégrer à la todo-list
            // on va pas mettre une ligne vide
            if(this.task.length === 0) {
                return
            }
            this.tasksCopy.push({name: this.task, status: "to-do"})
            this.task = null
        },
    },
}
</script>