<template>
    <div>
      <h2>Lista de Itens</h2>
      <ul>
        <li v-for="(item, index) in items" :key="index">
          <strong>{{ item.name }}</strong>: {{ item.description }}
        </li>
      </ul>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      items: Array,
    },
  };
  </script>
  