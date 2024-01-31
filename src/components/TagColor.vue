<template>
    <span class="tag-color">
        {{ texto }}
    </span>
</template>

<script lang="ts">
export default {
     name: "TagColor",
        props: {
            texto: { type: String, required: true }
        }
    }
</script>

<style scoped>
    
.tag-color {
  display: inline-block;
  border-radius: 0.5rem;
  min-width: 4.25rem;
  padding: 0.5rem;
  text-align: center;
  transition: 0.2s;
  color: var(--creme, #fffaf3);
  background: var(--coral, #f0633c);
  font-weight: 700;
}

</style>