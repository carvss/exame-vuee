<template>
    <div>
      <h2>Cadastro de Itens</h2>
      <form @submit.prevent="addItem">
        <label for="name">Nome:</label>
        <input v-model="name" id="name" type="text" required />
  
        <label for="description">Descrição:</label>
        <input v-model="description" id="description" type="text" required />
  
        <button type="submit">Adicionar Item</button>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        name: '',
        description: '',
      };
    },
    methods: {
      addItem() {
        this.$emit('item-added', {
          name: this.name,
          description: this.description,
        });
        this.name = '';
        this.description = '';
      },
    },
  };
  </script>
  