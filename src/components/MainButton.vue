<script lang="ts">
export default {
    props: {
        text: {
            type: String,
            required: true
        }
    }
}
</script>


<template>
    <button>
        {{ text }}
    </button>
</template>