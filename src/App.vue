<template>
    <favorite-body :card-list-data="favoriteSources" />

    <task-one />

    <task-two />
</template>

<script>
import FavoriteBody from './components/FavoriteBody.vue'
import { favoriteSources } from '@/constants/favorite_link'

import TaskOne from './components/TaskOne/index'
import TaskTwo from './components/TaskTwo/index'

export default {
    name: 'App',
    components: {
        FavoriteBody,
        TaskOne,
        TaskTwo,
    },
    data() {
        return {
            favoriteSources,
        }
    },
}
</script>

<style lang="scss">
// #app {
//     font-family: Avenir, Helvetica, Arial, sans-serif;
//     -webkit-font-smoothing: antialiased;
//     -moz-osx-font-smoothing: grayscale;
//     text-align: center;
//     color: #2c3e50;
//     margin-top: 60px;
// }
</style>
