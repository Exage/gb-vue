<template>
    <div class="container">
        <div class="product-details">
            <div class="product-details__info">
                <h1 class="product-details__title">
                    {{ product.title }}
                </h1>
                <h3 class="product-details__price">
                    {{ formattedPrice }}
                </h3>
            </div>
            <div class="product-details__available" :class="{ available: product.available }">
                <template v-if="product.available">
                    Available
                </template>
                <template v-if="!product.available">
                    Out of stock
                </template>
            </div>
        </div>
    </div>
</template>
<script>
export default {
    data() {
        return {
            product: {
                title: "iPhone 20 ultra",
                price: 999.99,
                available: true
            }
        }
    },
    computed: {
        formattedPrice() {
            return `$${this.product.price.toFixed(2)}`
        }
    }
}
</script>
<style lang="scss" scoped>
.product-details {
    display: flex;
    align-items: center;
    justify-content: space-between;

    padding: 10px 20px;

    border: 2px solid #d8d8d8;

    border-radius: 10px;

    &__title {
        font-size: 24px;
    }

    &__price {
        font-size: 14px;

        margin-top: 4px;
    }

    &__available {
        padding: 10px 20px;
        background-color: #d8d8d8;

        border-radius: 10px;

        &.available {
            color: #fff;
            background-color: #11e268;
        }
    }
}
</style>