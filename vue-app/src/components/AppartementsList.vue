<template>
    <ul class="appartements__list">
        <AppartementsItem v-for="item in items" 
            :key="item.id"
            :description="item.description"
            :price="item.price"
            :rating="item.rating"
            :url="item.url"
            />
    </ul>
</template>

<script>
import AppartementsItem from './AppartementsItem'

    export default {
        name: 'AppartementsList',
        components: {
            AppartementsItem
        },
        props: {
            items: {
                type: Array,
                default: () => []
            }
        }
    }
</script>

<style lang="scss">
    .appartements {
        &__list {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
            grid-gap: 1rem;
            padding: 0;
        }
    }
</style>