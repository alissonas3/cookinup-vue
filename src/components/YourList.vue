<template>
    <section>
      <span class="subtitulo-lg sua-lista-texto">
        Sua Lista de Ingredientes
      </span>

      <ul v-if="listaIngredientes.length" class="ingredientes-sua-lista">
        <li v-for="ingrediente in listaIngredientes" :key="ingrediente">
          <TagColor :textos="ingrediente" active />
        </li>
      </ul>
      <p v-else class="paragrafo lista-vazia">
        <img src="../assets/icones/lista-vazia.svg" alt="Ícone de pesquisa">
        Sua lista está vazia. Selecione os ingredientes disponíveis para visualizar
        as receitas.
      </p>
    </section>
</template>

<script lang="ts">
import type { PropType } from 'vue';
import TagColor from './TagColor.vue';

export default {
    name: "SuaLista",
    props: {
       listaIngredientes : { type: Array as PropType<string[]>, required: true }
    },

    components: {
      TagColor
    }
}

</script>

<style scoped>
.sua-lista-texto {
  color: var(--coral, #f0633c);
  display: block;
  text-align: center;
  margin-bottom: 1.5rem;
}

.ingredientes-sua-lista {
  display: flex;
  justify-content: center;
  gap: 1rem 1.5rem;
  flex-wrap: wrap;
}

.lista-vazia {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.25rem;

  color: var(--coral, #f0633c);
  text-align: center;
}

@media only screen and (max-width: 1300px) {
  .conteudo-principal {
    padding: 5rem 3.75rem;
    gap: 3.5rem;
  }
}

@media only screen and (max-width: 767px) {
  .conteudo-principal {
    padding: 4rem 1.5rem;
    gap: 4rem;
  }
}

</style>