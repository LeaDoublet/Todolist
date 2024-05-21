<script setup>
import Chose from "../Chose";
import { reactive } from 'vue';
import ToDoListItem from './ToDoListItem.vue';
import ToDoForm from './ToDoForm.vue';

const listeC = reactive([
    new Chose("menage"), 
    new Chose("Vaiselle")
]);

const handleToggleFait = (chose) => {
    chose.faire();
};

const handleDelete = (chose) => {
    const index = listeC.indexOf(chose);
    if (index > -1) {
    listeC.splice(index, 1);
    }
};

const handleAddChose = (texte) => {
    listeC.push(new Chose(texte));
}
</script>

<template>
    <h3>Liste des choses à faire</h3>
    <ToDoForm @add-chose="handleAddChose"/>
    <ul>
    <ToDoListItem
        v-for="chose in listeC"
        :key="chose.id"
        :chose="chose"
        @toggle-fait="handleToggleFait"
        @delete-chose="handleDelete"
    />
    </ul>
</template>

<style scoped>
/* Ajoutez des styles ici si nécessaire */
</style>
