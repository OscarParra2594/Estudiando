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
    <h1 class="text-center flex justify-center mb-6">Notas</h1>
    <div class="flex justify-center space-x-4 mb-4">
        <button @click="setHorizontal" class="bg-green-300 text-white px-4 py-4 rounded">Horizontal</button>
        <button @click="setVertical" class="bg-green-300 text-white px-4 py-4 rounded">Vertical</button>
    </div>
    <div :class="isHorizontal ? 'grid grid-cols-3 gap-4 mx-auto w-[500px] h-[400px]' : 'grid grid-rows-3 gap-4 mx-auto w-[700px]'">        
        <div v-for="number in cards" :key="number" :class="isHorizontal ? 'border p-2 bg-green-600 text-3x1 justify-center items-center' : 'border p-4 bg-green-600 flex text-3x1 justify-start items-center'">
                <div :class="isHorizontal ? 'bg-white h-[100px] w-[140px] ' : 'bg-white h-[50px] w-[50px] mx-2' "></div>
                {{ number || '' }}    
        </div> 
    </div>    
</template>