<script setup>
import { ref } from 'vue';
import { defineEmits } from 'vue';

const newChoseText = ref('');
const emit = defineEmits(['add-chose']);

const handleSubmit = () => {
    if (newChoseText.value.trim() !== '') {
    emit('add-chose', newChoseText.value);
    newChoseText.value = '';
    }
};
</script>

<template>
    <div>
        <input v-model="newChoseText" placeholder="Nouvelle chose à faire" />
        <button @click="handleSubmit">Ajouter</button>
    </div>
</template>

