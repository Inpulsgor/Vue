<template>
    <li class="appartement__item item">
        <div class="item__inner">
            <img class="item__image" :src="imageSrc" alt="appartement image">
            <div class="item__content">
                <p class="item__description">{{description}}</p>
                <div class="item__rating">
                    <RatingStars :rating="rating" />
                </div>
                <span class="item__price">UAH {{price}}</span>
            </div>
        </div>
    </li>
</template>

<script>
import RatingStars from './RatingStars'

    export default {
        name: 'AppartementItem',
        props: {
            description: {
                type: String,
                default: ''
            },
            rating: {
                type: Number,
                default: 0
            },
            price: {
                type: Number,
                required: true
            },
            imageSrc: {
                type: String,
                default: ''
            },
        },
        components: {
            RatingStars
        }
    }
</script>

<style lang="scss" scoped>
    .item {
        list-style: none;
        position: relative;
        max-width: 350px;
        padding: 0 20px;

        &__inner {
            position: relative;
        }

        &__image {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }

        &__content {
            cursor: pointer;
            position: relative;
            line-height: 1.4;
            text-align: center;
            z-index: 1;
            padding: 20px;
            min-height: 200px;
            opacity: 0;
            color: #fff;
            background: rgba(#0f1d2d, 0.7);
            transition: opacity 0.4s;

            &:hover {
                opacity: 1;
            }
        }
    }
</style>