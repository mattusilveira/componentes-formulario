<script setup>
import { reactive } from 'vue'

const emit = defineEmits
const produto = reactive({
    nome: '',
    preco: ''
})

function salvar() {
    if (produto.nome === '') {
        alert('O produto não pode ser vazio')
        return
    }
    emit()
}
</script>

<template>
    <form @submit.prevent="">
        <div>
            <label for="nome">Nome</label>
            <input type="text" id="nome" v-model="product.nome" />
        </div>
        <div>
            <label for="preco">Preço</label>
            <input type="text" id="preco" v-model="product.preco" />
        </div>
        <button type="submit">Salvar</button>
    </form>
</template>

<style scoped></style>