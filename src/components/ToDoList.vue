<script setup>
import Chose from "../Chose"
import { reactive } from 'vue';


const listeC = reactive([
    new Chose("menage"), 
    new Chose("Vaiselle")
    ]);

    const toggleFait = (chose) => {
        chose.faire();
};

// Function to delete a Chose item
const deleteChose = (chose) => {
    const index = listeC.indexOf(chose);
    if (index > -1) {
        listeC.splice(index, 1);
    }
};

</script>
<template>
    <h3>
        Liste des choses à faire
    </h3>
    <ul>
        <li v-for="chose in listeC" :key="chose.id">
            {{ chose.pourAfficher() }}
            <button @click="toggleFait(chose)">
                {{ chose.fait ? "Défaire" : " à Faire" }}
            </button>
            <button @click="deleteChose(chose)">Delete</button>
        </li>
    </ul>
</template>
