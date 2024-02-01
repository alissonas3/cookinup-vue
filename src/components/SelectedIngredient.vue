<template>
    <button class="ingrediente" @click="selectIngredientOnClick()"
    :aria-pressed="selecionado">
        <TagColor :textos="ingredienteSelecionado" :active="selecionado"/>
    </button>
</template>

<script lang="ts">
import TagColor from './TagColor.vue';

export default {
    name: "IngredienteSelecionado",
    components: {
        TagColor
    },
    data(){
        return {
            selecionado: false
        }
    },
    props: {
        ingredienteSelecionado: { type: String, required: true }
    },
    methods: {
        selectIngredientOnClick() {
            this.selecionado = !this.selecionado

            if(this.selecionado) {
                this.$emit('addIngredientes', this.ingredienteSelecionado);
            }
        }
    },
    emits: ['addIngredientes']

}

</script>

<style scoped>
.ingrediente {
    cursor: pointer;
}
</style>