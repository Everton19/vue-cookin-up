<script>
import { getCategories } from '@/http/index.ts'

export default {
    data(){
        return {
            categories: getCategories()
        }
    }
}

</script>

<template>
    <section class="select-ingredient">
        <h1 class="header-lg ingredients-title">
            Ingredientes
        </h1>

        <p class="subtitle-lg instruction">
            Selecione abaixo os ingredientes que você quer usar nesta receita:
        </p>

        <ul class="categories">
            <li v-for="category in categories" :key="category.rotulo">
                {{ category.nome }}  
            </li>
        </ul>

        <p class="hints">
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
}

</style>