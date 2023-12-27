<script setup>
import { ref } from 'vue';

const user = ref({email:'' , senha:''});

const handlesubmit = ()=>{
 console.log(user.value);
user.value.email = ''
user.value.senha = ''
    }


</script>

<template>
<form   @submit.prevent="handlesubmit">
<input type="text" v-model="user.email">
<input type="password" v-model="user.senha">
<input type="submit" value="entrar">
</form>
</template>