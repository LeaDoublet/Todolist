<script setup>
import Chose from "../Chose"
import { reactive } from 'vue';


const listeC = reactive([
    new Chose("menage"), 
    new Chose("Vaiselle")
    ]);

</script>
<template>
    <h3>
        Liste des choses à faire
    </h3>
    <ul>
        <li v-for="chose in listeC" :key="chose.id">
            {{ chose.pourAfficher() }}
        </li>
    </ul>
</template>
