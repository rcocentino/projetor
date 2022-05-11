<script setup>
    const { data } = await useFetch('https://iaknkztrklguiswbybdy.supabase.co/rest/v1/Client', {
        headers: {
            apikey: 'eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJzdXBhYmFzZSIsInJlZiI6Imlha25renRya2xndWlzd2J5YmR5Iiwicm9sZSI6ImFub24iLCJpYXQiOjE2NTE3Njk2MDYsImV4cCI6MTk2NzM0NTYwNn0.6KVpOWvp9QAlZatHeudMKZM6Vhy1oZZF3nihHSi1Xrk'
        }
    })

    function sendMessage(id) {
        alert("O número clicado foi o: " + id)
    }
</script>

<template>
    <div v-for="cliente in data" v-bind:id="`harsh${cliente.cnpj}`">
        <button v-bind:id="`uuid-${cliente.id}`" v-on:click="sendMessage(`${cliente.id}`)">{{ cliente.nome }}</button>
    </div>

</template>