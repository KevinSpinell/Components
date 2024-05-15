<script setup>
    import { ref } from 'vue'
    const tasks = ref([]);
    const inputTasks = ref();
    function addTask(){
        tasks.value.push(inputTasks.value)
        inputTasks.value = ''
        console.log(tasks)
    }
</script>
<template>
    <div class="max-w-96 bg-slate-300 rounded shadow mx-auto mt-10  py-8 px-10">
        <h1 class="text-center text-lg font-semibold">
            Lista de Tareas
        </h1>
        <div class="mt-4 mb-2">
            <input type="text" class="w-4/5" v-model="inputTasks">
            <button class="w-1/5 bg-green-500 text-white font-bold" @click="addTask()">+</button>
        </div>
        <div 
            class="bg-white/60 px-2 py-2"
            v-for="(task, index) in tasks" :key="index"
        >
            {{task}}
        </div>
    </div>
</template>