<script setup>
    const { data } = await useFetch('https://iaknkztrklguiswbybdy.supabase.co/rest/v1/Client', {
        headers: {
            apikey: process.env.APIKEY
        }
    })
</script>

<template>
    <p>Olá, tudo bem?</p>
    <div v-for="cliente in data" v-bind:id="`harsh${cliente.cnpj}`">
        <button v-bind:id="`uuid-${cliente.id}`" v-on:click="sendMessage(`${cliente.id}`)">{{ cliente.nome }}</button>
    </div>
</template>