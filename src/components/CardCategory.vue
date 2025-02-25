<script lang="ts">
import type ICategory from '@/interfaces/ICategory';
import type { PropType } from 'vue';
import SelectedIngredient from '@/components/SelectedIngredient.vue';

export default {
    props: {
        category: {
            type: Object as PropType<ICategory>,
            required: true
        }
    },
    components: {
        SelectedIngredient
    }
}

</script>

<template>
    <article class="category">
        <header class="category-header">
            <img 
                :src="`/src/assets/images/ingredients/${category.imagem}`" 
                :alt="`${category.imagem}`" 
                class="category-image">
        </header>

        <h2 class="paragraph-lg category-name">
            {{ category.nome }}
        </h2>

        <ul class="category-ingredient">
            <li v-for="ingredient in category?.ingredientes" :key="ingredient">
              <SelectedIngredient :ingredient="ingredient"/>
            </li>
        </ul>
    </article>
</template>

<style scoped>
.category {
  width: 19.5rem;
  padding: 1rem;
  border-radius: 1rem;
  background: var(--white, #fff);
  box-shadow: 4px 4px 10px 0px rgba(68, 68, 68, 0.05);
  height: 100%;

  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 2rem;
}

.category-header {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0.5rem;
}

.category-image {
  width: 3.5rem;
}

.category-name {
  text-align: center;
  color: var(--medium-green, #3d6d4a);
  font-weight: 700;
}

.category-ingredient {
  display: flex;
  justify-content: center;
  gap: 0.5rem;
  flex-wrap: wrap;
}

</style>