<template>
    <div>
      <button @click="toggleForm">Mostrar/Esconder Formulário</button>
  
      <ItemForm v-show="showForm" @item-added="addItem" />
      <ItemList :items="items" />
    </div>
  </template>
  
  <script>
  import ItemForm from '@/src/components/ItemForm.vue';
  import ItemList from '@/src/components/ItemList.vue';
  
  export default {
    components: {
      ItemForm,
      ItemList,
    },
    data() {
      return {
        showForm: true,
        items: [],
      };
    },
    methods: {
      toggleForm() {
        this.showForm = !this.showForm;
      },
      addItem(item) {
        this.items.push(item);
      },
    },
  };
  </script>
  