<script lang="ts">
import SelectIngredient from '@/components/SelectIngredient.vue';
import Tag from '@/components/Tag.vue';
import ShowRecipes from './ShowRecipes.vue';

type Page = 'Show Recipes' | 'Select Ingredients';

export default {
    data(){
        return {
            ingredients: [] as string[],
            content: 'Select Ingredients' as Page
        }
    },
    methods: {
        addIngriedient(ingredient: string){
            this.ingredients.push(ingredient);
        },

        removeIngredient(ingredient: string){
            this.ingredients = this.ingredients.filter((item) => item !== ingredient);
        },

        searchRecipes(page: Page){
            this.content = page;
        }
    },
    components: {
        SelectIngredient,
        Tag,
        ShowRecipes
    }
}
</script>

<template>
    <main class="main">
        <section>
            <span class="subtitle-lg list">
                Sua lista:
            </span>

            <ul v-if="ingredients.length" class="list-ingredient">
                <li 
                    v-for="ingredient in ingredients" :key="ingredient">
                    <Tag :text="ingredient" :active="true"/>
                </li>
            </ul>

            <p v-else class="paragraph empty-list">
                <img src="../assets/images/empty-list.svg" alt="">
                Sua lista está vazia, selecione ingredientes para iniciar.
            </p>
        </section>
        
        <SelectIngredient v-if="content === 'Select Ingredients'"
            @add-ingredient="addIngriedient($event)"
            @remove-ingredient="removeIngredient($event)"
            @search-recipes="searchRecipes('Show Recipes')"
        /> 

        <ShowRecipes v-else-if="content == 'Show Recipes'"/>
    </main>
</template>

<style scoped>
.main {
    padding: 6.5rem 7.5rem;
    border-radius: 3.75rem 3.75rem 0 0;
    background-color: var(--cream);
    color: gray;
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 5rem;
}

.list {
    color: var(--coral);
    display: block;
    text-align: center;
    margin-bottom: 1.5rem;
}

.list-ingredient {
    display: flex;
    justify-content: center;
    gap: 1rem 1.5rem;
    flex: wrap;
}

.empty-list {
  display: flex;
  justify-content: center;
  align-items: center;
  flex-wrap: wrap;
  gap: 0.25rem;

  color: var(--coral, #f0633c);
  text-align: center;
}

@media only screen and (max-width: 1300px) {
    .main {
        padding: 5rem 3.75rem;
        gap: 3.5rem;
    }
}

@media only screen and (max-width: 767px) {
    .main {
        padding: 4rem 1.5rem;
        gap: 4rem;
    }
}
</style>