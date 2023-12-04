<template>
    <button @click="deleteTask(index)">Supprimer</button>
</template>

<script>
export default {
    name: 'DeleteComponent',
    props: {
        tasks: Array,
        index: Number
    },

    data() {
        return {
            // comme on ne peut pas modifier un props, on en fait une copie
            // avec tasksCopy: this.tasks où, this.tasks
            // est la propriété de l'objet Data provenant de l'App.Vue
            tasksCopy: this.tasks
        }
    },
    methods: {
        deleteTask(index){
            // soit on met index en argument et on peut écrire splice(index,1)
            // soit on ne met pas index en argument et on écrit splice(this.index)
            this.tasksCopy.splice(index, 1);
        },
    },
}
</script>
