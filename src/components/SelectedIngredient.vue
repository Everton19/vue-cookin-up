<script lang="ts">
import Tag from '@/components/Tag.vue';

export default {
    props: {
        ingredient: {
            type: String,
            required: true
        }
    },
    methods: {
        onClick() {
            this.selected = !this.selected;

            if (this.selected) {
                this.$emit('addIngedient', this.ingredient);
            } else {
                this.$emit('removeIngedient', this.ingredient);
            }
        }
    },
    emits: ['addIngedient', 'removeIngedient'],
    data() {
        return {
            selected: false
        }
    },
    components: {
        Tag
    },
}

</script>

<template>
    <button class="ingredient" @click="onClick" :aria-pressed="selected">
        <Tag :text="ingredient" :active="selected" />
    </button>
</template>

<style scoped>
.ingredient {
    cursor: pointer;
}
</style>