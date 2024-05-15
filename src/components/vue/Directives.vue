<script setup>
    import { ref } from 'vue';
    let msg = ref('Soy un tooltip'); 
    let checked = ref(false)
    let data = ["Hola", "Mundo", "Bonito"]
    let filtered = data.filter((word) => word.includes('M'))
    let filterede = data.filter(function (word) { 
        return word.includes('B')
    })
</script>

<template>
    <input 
        class="border-2 "
        v-model="msg"
        :class="{'border-red-500':checked}"
    >
    <div :title="msg">
        {{ msg }}
    </div>
    <label for="check">Seleccionado {{ checked }}</label>
    <input type="checkbox" v-model="checked"/>

    <ul>
        <li :id ="index" class="text-blue-500" v-for="(text, index) in data" :key="index"> {{(index+1) +" " + text }}</li>
        <li :id ="index" class="text-red-500" v-for="(text, index) in filtered" :key="index"> {{(index+1) +" " + text }}</li>
        <li :id ="index" class="text-green-500" v-for="(text, index) in filterede" :key="index"> {{(index+1) +" " + text }}</li>
    </ul>

</template>