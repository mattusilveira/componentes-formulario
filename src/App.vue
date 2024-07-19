<script setup>
import { ref } from 'vue'
import ProductList from '@/components/ProductList.vue'

const produtos = ref([
  { id: 1, nome: 'Produto 1', preco: 'R$ 20,50' },
  { id: 2, nome: 'Produto 2', preco: 'R$ 120,50' },
  { id: 3, nome: 'Produto 3', preco: 'R$ 220,50' },
  { id: 4, nome: 'Produto 4', preco: 'R$ 320,50' },
])

function excluir(id) {
  const index = produtos.value.findIndex(produto => produto.id === id)
  produtos.value.splice(index, 1)
}

function excluirTodos() {
  produtos.value = []
}
</script>

<template>
  <h1>Meus Produtos</h1>
  <product-list :produtos="produtos" @excluir="excluir" @apagarTudo="excluirTodos" />
</template>

<style scoped></style>