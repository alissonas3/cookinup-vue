<template>
  <main class="conteudo-principal">

    <SuaLista :listaIngredientes="ingredientes"/>
    <SelectIngredients @addIngredientes="addIngredient"/>
    <SearchReceipts />
    
  </main>
</template>

<script lang="ts">
import SearchReceipts from './SearchReceipts.vue';
import SelectIngredients from "./SelectIngredients.vue";
import SuaLista from './YourList.vue';

export default {
  name: "MainContent",

  data() {
    return {
      ingredientes: [] as string[],
    };
  },
  components: {
    SelectIngredients,
    SuaLista,
    SearchReceipts,
  },
  methods: {
    addIngredient(ingrediente: string) {
      this.ingredientes.push(ingrediente)
    }
  }
};
</script>

<style scoped>
.conteudo-principal {
  padding: 6.5rem 7.5rem;
  border-radius: 3.75rem 3.75rem 0rem 0rem;
  background: var(--creme, #fffaf3);
  color: var(--cinza, #444);
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 5rem;
}
</style>