<script lang="ts">
import Tag from '@/components/Tag.vue';

export default {
    props: {
        ingredient: {
            type: String,
            required: true
        }
    },
    components: {
        Tag
    },
    data() {
        return {
            selected: false
        }
    }
}

</script>

<template>
    <button class="ingredient" @click="!selected" :aria-pressed="selected">
        <Tag :text="ingredient" :active="selected" />
    </button>
</template>

<style scoped>
.ingredient {
    cursor: pointer;
}
</style>