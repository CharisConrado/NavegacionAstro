<script setup>
import { ref } from 'vue';
const name = "Pepito"
let counter = ref(0)
let lista

let characters = ref([])
function res(){
    counter.value--
    console.log(counter)
    
}
function add(){
    counter.value++
    console.log(counter)
    characters.value.push(counter.value)
    console.log(characters)
}



</script>

<template>

    <div
     class="mx-auto max-w-96  rounded py-4 px-6 bg-blue-300">Hola {{ name }}
        <div v-if="counter>0" class=" bg-blue-600 text-white size-8 rounded-full flex items-center justify-center">

            {{ counter }}

        </div>
        <div v-else>
            Nadie te excribe
        </div>
        <div 
           
           @click="add"
        
          class="bg-green-600 text-white size-8 rounded-full flex items-center justify-center cursor-pointer"
        >
        +
        </div>
        <div @click="res" class="bg-red-600 text-white size-8 rounded-full flex items-center justify-center cursor-pointer">-</div>
        


        
    </div>
    <div v-for="(name, index) in characters":key="index"
    class="bg-green-500 mb-1">{{ name }}</div>

   

</template>