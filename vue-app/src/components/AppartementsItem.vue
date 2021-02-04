<template>
    <li class="appartements__item item">
        <div class="item__inner">
            <img class="item__image" :src="url" alt="appartement image">
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
            url: {
                type: String,
                default: ''
            },
        },
        components: {
            RatingStars
        }
    }
</script>

<style lang="scss">
    .item {
        position: relative;
        list-style: none;

        &__inner {
            position: relative;
            width: 100%;
            height: auto;
        }

        &__image {
            object-fit: cover;
            width: 100%;
            height: 100%;
        }

        &__content {
            object-fit: fill;
            width: 100%;
            height: 100%;
            position: absolute;
            left: 0;
            top: 0;
            right: 0;
            bottom: 0;
            cursor: pointer;
            line-height: 1.4;
            text-align: center;
            z-index: 1;

            min-height: 200px;
            opacity: 0;
            color: #fff;
            background: rgba(#0f1d2d, 0.7);
            transition: opacity 0.4s;

            &:hover {
                opacity: 1;
            }
        }

        &__description {
            margin-bottom: 20px;
            max-height: calc(1em * 1.4 * 3);
            overflow: hidden;
        }

        &__rating {
            margin-bottom: 20px;
        }

        &__price {
            font-size: 20px;
            font-weight: 600;
        }
    }
</style>