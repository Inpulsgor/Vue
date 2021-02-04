<template>
    <div class="stars-rating">
        <i class="star star--outlined" v-for="index in starLimit" :key="index" ></i>
        <div class="stars-rating__fullfilled" :style="ratingWidthStyle">
            <i class="star star--colored" v-for="index in starLimit" :key="index"></i>
        </div>
    </div>
</template>

<script>
    export default {
        name: 'RatingStars',
        props: {
            rating: {
                type: Number,
                default: 0
            },
            starLimit: {
                type: Number,
                default: 5
            }
        },
        computed: {
            retingWidth() {
                return this.rating / this.starLimit * 100;
            },
            ratingWidthStyle() {
                return `width: ${this.retingWidth}%`
            }
        }
        
    }
</script>

<style lang="scss" scoped>
.stars-rating {
    position: relative;
    display: inline-flex;

    &__fullfilled {
        display: inline-flex;
        position: absolute;
        width: 0;
        height: 100%;
        left: 0;
        top: 0;
        overflow: hidden;
    }
}

.star {
    display: inline-block;
    width: 24px;
    height: 24px;
    margin: 0 5px;
    flex-shrink: 0;

    &--colored {
        background: url('../assets/icons/star.svg') center no-repeat;
    }
    &--outlined {
         background: url('../assets/icons/empty.svg') center no-repeat;
    }
}

</style>