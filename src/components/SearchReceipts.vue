<template>
    <button class="btn-color">
        <span class="">Buscar Receitas!
            <!-- <TagColor  active/> -->
        </span>
    </button>    
</template>


<script lang="ts">
// import TagColor from './TagColor.vue'

export default {
    name: "BuscarReceitas",
    // components: TagColor
}

</script>

<style scoped>
.btn-color {
  width: 20.5rem;
  padding: 0.5rem;
  border-radius: 5px;
  cursor: pointer;
  color: var(--creme, #fffaf3);
  background: var(--coral, #f0633c);
  font-weight: 700;
}
</style>