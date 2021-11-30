<template>
    <div class="cards">       
        <article class="card">
            <header>
                <h2>{{product.name}}</h2>
            </header>    
            <img :src="product.img" alt={{product.img}}>
            <div class="content">
                <p>PHP. {{product.price}}.00</p>
            </div>
            <footer>
                <button class="favorite styled" @click="$emit('view-product', product)">
                    Item Details
                </button>
            </footer>
        </article>
    </div>
</template>

<script>
    export default {
        props: ['product'],
    }
</script>

<style scoped>
    .card {
        height: 400px;
        margin: 20px;
        padding: 10px 20px;
        border-radius: 10px;
        background: #e0e0eb;
        box-shadow: 20px 20px 20px #14141f;
    }

    .card img {
        object-fit: cover;
        width: 100%;
        height: 200px;
    }
    .styled {
        border: 0;
        line-height: 2.5;
        padding: 0 20px;
        font-size: 1rem;
        text-align: center;
        color: #fff;
        text-shadow: 1px 1px 1px #000;
        border-radius: 10px;
        background-color: #00b3b3;
        background-image: linear-gradient(to top left,
                                        rgba(0, 0, 0, .2),
                                        rgba(0, 0, 0, .2) 30%,
                                        rgba(0, 0, 0, 0));
        box-shadow: inset 2px 2px 3px rgba(255, 255, 255, .6),
                    inset -2px -2px 3px rgba(0, 0, 0, .6);
        cursor: pointer;
    }

    .styled:hover {
        background-color: #003333;
    }

    .styled:active {
        box-shadow: inset -2px -2px 3px rgba(255, 255, 255, .6),
                    inset 2px 2px 3px rgba(0, 0, 0, .6);
    }
</style>