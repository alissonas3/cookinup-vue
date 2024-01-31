<template>
  <section class="selecionar-ingredientes">
    <h2 class="titulo-ingredientes">Ingredientes</h2>
    <p class="instrucoes">
      Selecione abaixo os ingredientes que você quer usar nesta receita.
    </p>

    <ul class="categorias">
      <li v-for="categoria in categorias" :key="categoria.nome">
        <CardCategoria :categoria="categoria"/>
      </li>
    </ul>

    <p class="paragrafo dicas">
      *Atenção: Consideramos que você tenha em casa os ingredientes: sal,
      pimenta e água.
    </p>
  </section>
</template>

<script lang="ts">
import { categoriaDeIngredientes } from "@/api/index.ts";
import type ICategory from "@/interfaces/ICategory";
import CardCategoria from "@/components/CategoryCard.vue";

export default {
  name: "SelectIngredients",

  data() {
    return {
      categorias: [] as ICategory[],
    };
  },

  components: {
    CardCategoria,
  },
  
  async created() {
    this.categorias = await categoriaDeIngredientes();
  },
};
</script>

<style scoped>
.selecionar-ingredientes {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.titulo-ingredientes {
  color: var(--verde-medio, #3d6d4a);
  display: block;
  margin-bottom: 1.5rem;
}

.instrucoes {
  margin-bottom: 2rem;
}

.categorias {
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.dica {
  align-self: flex-start;
  margin-bottom: 3.5rem;
}

@media only screen and (max-width: 767px) {
  .dica {
    margin-bottom: 2.5rem;
  }
}
</style>