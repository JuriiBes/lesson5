<template>
    <div class="proposition__notebook">
        <notebooks-body :data-notebooks="notebooksList" />
    </div>
</template>

<script>
import { notebooksList } from '@/constants/notebooks_data.js'
import NotebooksBody from '@/components/TaskTwo/NotebooksBody.vue'

export default {
    name: 'TaskTwo',
    components: {
        NotebooksBody,
    },
    data() {
        return {
            notebooksList,
        }
    },
}
</script>

<style lang="scss" scoped>
.proposition {
    // .proposition__notebook
    &__notebook {
        padding: 15px;
    }
}
</style>
