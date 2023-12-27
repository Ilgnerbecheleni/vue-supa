<script setup>
import { supabase } from '../../supabase';
import { onMounted, ref } from 'vue';

const nomes = ref([]);
const listar = async ()=>{
  
let { data: agenda, error } = await supabase
  .from('agenda')
  .select('*')
    nomes.value = agenda
    console.log(agenda)
  }

  onMounted(() => {
    listar()
  })


const msg = import.meta.env.VITE_SOME_KEY;
console.log(msg);
</script>

<template>
  <main>
    <ul>
      <li v-for="nome in nomes" :key="nome.id">{{ nome.nome }}</li>
    </ul>
  </main>
</template>
