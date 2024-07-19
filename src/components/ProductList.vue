<script setup>
defineProps(['produtos'])
</script>

<template>
    <table>
        <thead>
            <tr>
                <th>Nome</th>
                <th>Preço</th>
                <th>Ações</th>
            </tr>
        </thead>

        <body>
            <tr v-for="produto in produtos" :key="produto.id">
                <td>{{ produto.nome }}</td>
                <td>{{ produto.preco }} </td>
                <td><i class="mdi mdi-delete" @click="$emit('excluir', produto.id)" /></td>
            </tr>
        </body>
    </table>
    <button @click="$emit('apagarTudo')">Apagar tudo</button>
</template>

<style scoped>
tr i {
    cursor: pointer;
}
</style>