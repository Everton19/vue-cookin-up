<script lang="ts">
import { getCategories } from '@/http/index';
import type ICategory from '@/interfaces/ICategory';
import CardCategory from './CardCategory.vue';

export default {
    data(){
        return {
            categories: [] as ICategory[]
        }
    },
    async created(){
        this.categories = await getCategories();
    },
    emits: ['addIngredient', 'removeIngredient'],
    components: {
        CardCategory
    }
}

</script>

<template>
    <section class="select-ingredient">
        <h1 class="header ingredients-title">
            Ingredientes
        </h1>

        <p class="paragraph-lg instruction">
            Selecione abaixo os ingredientes que você quer usar nesta receita:
        </p>

        <ul class="categories">
            <li v-for="category in categories" :key="category.nome">
                <CardCategory 
                    :category="category" 
                    @add-ingredient="$emit('addIngredient', $event)"
                    @remove-ingredient="$emit('removeIngredient', $event)"
                />
            </li>
        </ul>

        <p class="paragraph hint">
            *Atenção: consideramos que você tem em casa sal, pimenta e água.
        </p>
    </section>
</template>

<style scoped>

.select-ingredient {
    display: flex;
    flex-direction: column;
    align-items: center;
}

.ingredients-title {
    color: var(--medium-green, #3D6D4A);
    display: block;
    margin-bottom: 1.5rem;
}

.instruction {
    margin-bottom: 2rem;
}

.categories {
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}

.hint {
  margin: 1.5rem 0 3.5rem 0;
}

@media only screen and (max-width: 767px) {
  .hint {
    margin: 1.5rem 0 1.5rem 0;
  }
}
</style>