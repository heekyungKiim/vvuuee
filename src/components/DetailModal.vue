.<template>
  <div class="black-bg" v-if="isDetailOpened == true">
    <div class="white-bg">
      <img :src="products[productNumber].image" alt="">
      <h4>{{products[productNumber].title}}</h4>
      <h4>{{products[productNumber].content}}</h4>
      <h4>{{products[productNumber].price}}</h4>
      <!-- <button @click="isDetailOpened = false">close</button> -->
    </div>
  </div>
</template>
 
<script>
export default {
    name: "DetailModal",
    props:{
        products: Array,
    },
    data(){
        return{
        productNumber: 0,
        isDetailOpened: false
        }
    }
}
</script>

<style>

</style>