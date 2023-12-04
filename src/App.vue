<template>
    <div class="container">
        <h1>To-do list</h1>
        <!-- Add -->
        <add-component :tasks="tasks" v-if="isEditing"></add-component>

        <!-- Edit -->
        <edit-component :tasks="tasks" :isEditing="isEditing" :selectIndex="selectIndex" :editTask="editTask" @update-items = "UpdateItems" v-else></edit-component>

        <!-- Read -->
        <div>
            <table>
                <thead>
                    <tr>
                        <th>Task</th>
                        <th>Status</th>
                        <th colspan="2">Actions</th>
                    </tr>
                </thead>
                <tbody>
                    <tr v-for="(task, index) in tasks" :key="index">
                        <!-- <td>{{ task }}</td> -->
                        <td>{{ task.name }}</td>
                        <td class="changeStatus" @click="updateStatus">{{ task.status }}</td>
                        <td>
                            <button @click="update(index, task)">Modifier</button>
                        </td>
                        <td>
                            <!-- Delete -->
                            <delete-component :tasks="tasks" :index="index" ></delete-component>
                        </td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</template>

<script>
import AddComponent from "./components/AddComponent.vue"
import DeleteComponent from "./components/DeleteComponent.vue"
import EditComponent from "./components/EditComponent.vue"

export default {
    name: "App",
    components: {
        AddComponent,
        DeleteComponent,
        EditComponent
    },
    data() {
        return {
            // 2-
            // tasks: ["coucou 1", "test 2", "test 3"],
            tasks: [],
            selectIndex : null,
            isEditing: true,
            editTask : null,
        }
    },
    methods: {
        update(index, task) {
            this.isEditing = false
            this.selectIndex = index
            this.editTask = task
        },

        UpdateItems(isEditingCopy, selectIndexCopy) {
            console.log(isEditingCopy, selectIndexCopy)
            this.isEditing = isEditingCopy
            this.selectIndex = selectIndexCopy
        }
    }
}
</script>

<style>
.container {
    display: flex;
    flex-direction: column;
    text-align: center;
    align-items: center;
    margin: 20px;
    max-width: 100%;
}

.formContainer {
    max-width: 100%;
}

input {
    width: 80%;
    padding: 10px;
    text-align: center;
}

.btn {
    background: orange;;
    border: 1px solid black;
    width: 30%;
    border-radius: 5px;
    padding: 10px;
    text-transform: uppercase;
    cursor: pointer;
}

.changeStatus {
cursor: pointer;
}

button {
    cursor: pointer;
}

table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 20px;

}

thead {
    background-color: #f2f2f2;
}

th, td {
    border: 1px solid #000;
    padding: 8px;
    text-align: center;
}

tbody tr:nth-child(even) {
    background-color: #f2f2f2;
}

.fa-pen:hover{
    cursor: pointer;
}
</style>