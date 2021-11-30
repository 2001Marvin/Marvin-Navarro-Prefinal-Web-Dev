<template>
  <div class="home">
    <ItemDescription  :product="product" :active="active.productbox" v-on:closeItemBox="closeItemBox()" />
    <div class="container">
        <div class="card">
            <Prod v-for="product in items" :key="product.id" :product="product" v-on:view-product="viewProd($event)" />
        </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import items from '../data/items.js';
import Prod from '../components/products/Prod.vue';
import ItemDescription from '../components/products/ItemDescription.vue';

export default {
  name: "Home",
  components: {
    Prod,ItemDescription
  },
  data() {
    return {
      items: items,
      product: null,
      active: {
        productbox : false
      }
    }
  },
  methods: {
    viewProd(product){
      this.product = product
      this.active.productbox = true
      console.log(this.product);
    },
    closeItemBox(){
      this.active.productbox = false
    }
  }
};
</script>

<style scoped>
    .mainBox{
        display: flex;
    }
    .container{
        display: flex;
        justify-content: center;
    }
    .card{ 
      display: grid;
      grid-template-columns: 1fr 1fr 1fr;
      
    }

</style>
