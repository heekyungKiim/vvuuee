<template>
  <div class="menu">
    <a v-for="(menu, idx) in menus" :key="idx">{{idx+1}}.{{menu}}</a>
  </div>
  <DiscountBanner/>
  <div v-for='(prod, idx) in products' :key ="idx">
    <!-- <img :src="products[idx].image" alt="" class="room-img "> -->
    <h4 @click="isDetailOpened = true; productNumber = idx ">{{products[idx].title}}</h4>
    <p>{{products[idx].price}}</p>
  </div>

<DetailModal :products='products' :productNumber="productNumber" :isDetailOpened="isDetailOpened"/>
  
</template>

<script>
import products from './assets/database'
import DetailModal from './components/DetailModal.vue'
import DiscountBanner from './components/DiscountBanner.vue'

export default {
  name: 'App',
  components: {
    DiscountBanner,
    DetailModal
  },
  data(){
    return{
      productNumber : 0,
      isDetailOpened : false,
      products,
      menus : ['Home', 'Shop', 'About']
    }
  },
  // method
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
.menu{
  background: darkslateblue;
  padding: 15px;
  border-radius: 5px;
}
.menu a{
  color: white;
  padding: 10px;
}


/* .black-bg{
  width: 100%; height: 100%;
  background: rgba(0,0,0,0.5);
  position: fixed; 
  padding: 20px;
}

.white-bg {
  width: 100%;
  background: white;
  border-radius: 8px;
  padding:20px
} */
</style>
