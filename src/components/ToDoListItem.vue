<script setup>
import { defineProps, defineEmits } from 'vue';

const props = defineProps(['chose']);
const emit = defineEmits(['toggle-fait', 'delete-chose']);

const handleToggleFait = () => {
    emit('toggle-fait', props.chose);
};

const handleDelete = () => {
    emit('delete-chose', props.chose);
};
</script>

<template>
    <li>
    {{ chose.pourAfficher() }}
    <button @click="handleToggleFait">{{ chose.fait ? "Défaire" : "À Faire" }}</button>
    <button @click="handleDelete">Delete</button>
    </li>
</template>

<style scoped>
/* Ajoutez des styles ici si nécessaire */
</style>
