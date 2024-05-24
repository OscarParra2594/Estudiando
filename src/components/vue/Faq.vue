<script setup>
import { ref } from 'vue'

const cards = ref(['Nota1', 'Nota2', 'Nota3', 'Nota4', 'Nota5', 'Nota6'])
const isHorizontal = ref(true)

function setHorizontal(){
    isHorizontal.value = true;
}

function setVertical(){
    isHorizontal.value = false;
}

</script>

<template>
    <div class="flex justify-center space-x-4 mb-4">
        <button @click="setHorizontal" class="bg-green-300 text-white px-4 py-4 rounded">Horizontal</button>
        <button @click="setVertical" class="bg-green-300 text-white px-4 py-4 rounded">Vertical</button>
    </div>
    <div :class="isHorizontal ? 'grid grid-cols-3 gap-4' : 'grid grid-rows-3 gap-4'">        
        <div v-for="number in cards" :key="number" class="border p-4 bg-green-600 text-3x1 flex justify-center items-center">             
                {{ number || '' }}    
        </div> 
    </div>    
</template>