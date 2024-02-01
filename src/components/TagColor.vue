<template>
    <span :class="['tag-color', { active }]">
        {{ textos }}
    </span>
</template>

<script lang="ts">
export default {
     name: "TagColor",
        props: {
            textos: { type: String, required: true },
            active: Boolean
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
  color: var(--cinza);
  background-color: var(--cinza-claro);
  font-weight: 400;
}

.active {
  color: var(--creme, #fffaf3);
  background: var(--coral, #f0633c);
  font-weight: 700;
}

</style>