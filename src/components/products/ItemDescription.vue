<template>
        
    <div class="drawer" :class="{show: active}">

        <div v-if="product" class="prodDetails">
            <h3 class="text-center">{{ product.name }}</h3>
            <p class="description">{{ product.desc }}</p>
            <h3 class="text-center">${{ product.price.toFixed(2) }}</h3>

            <div class="cartTotal" v-if="prodTotal">
                <h3>In Cart</h3>
                <h4>{{ prodTotal }}</h4>
            </div>

            <div class="buttons">
                <button class="add">Add Item</button>
                <button class="remove">Remove Item</button>
            </div>
        </div>
    </div>
</template>

<script>
    export default {
        props: ['product', 'active'],
        computed: {
            prodTotal() {
                return 5
            }
        }
    }   
</script>

<style scoped>

    .drawer{
        margin: 10px auto;
        padding: 10px 20px;
        background: #61627d;
        width: 50%;
        color: #fff;
    }
    .add{
        height: 55px;
        width: 100px;
        background: #41b524;
        border: none;
        border-radius: 5px;
        margin: 5px;
        cursor: pointer;
    }
    .remove{
        height: 55px;
        width: 100px;
        background: #ab2929;
        color: #fff;
        border: none;
        border-radius: 5px;
        margin: 5px;
        cursor: pointer;
    }

</style>