<template>
    <div class="notebooks__body">
        <notebook-card v-for="notebook in dataNotebooks" :key="notebook.id" :notebook-card-data="notebook" />
    </div>
</template>

<script>
import NotebookCard from '@/components/TaskTwo/NotebookCard.vue'

export default {
    name: 'NotebooksBody',
    components: {
        NotebookCard,
    },
    props: {
        dataNotebooks: {
            type: Array,
            default: () => [],
        },
    },
}
</script>

<style lang="scss" scoped>
.notebooks {
    // .notebooks__body
    &__body {
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
    }
}
</style>
