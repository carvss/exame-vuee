<script setup>
import { ref } from 'vue';
import ItemForm from '.src/components/ItemForm.vue';
import ItemList from '.src/components/ItemList.vue';
</script>

<template>
  <header>
    <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
    <h1>Gestão de Itens</h1>
  </header>

  <main>
    <button class="toggle-button" @click="showForm = !showForm">
      {{ showForm ? "Esconder Formulário" : "Mostrar Formulário" }}
    </button>

    <ItemForm v-show="showForm" @item-added="addItem" />
    <ItemList :items="items" />
  </main>
</template>

<script>
const items = ref([]);
const showForm = ref(true);

function addItem(item) {
  items.value.push(item);
}
</script>

<style scoped>
header {
  line-height: 1.5;
  text-align: center;
  margin-bottom: 2rem;
}

.logo {
  display: block;
  margin: 0 auto 1rem;
}

h1 {
  margin: 0;
  font-size: 1.5rem;
  color: #42b883;
}

main {
  padding: 1rem;
}

.toggle-button {
  display: block;
  margin: 1rem auto;
  padding: 0.5rem 1rem;
  background-color: #42b883;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.toggle-button:hover {
  background-color: #2c7a75;
}
</style>
