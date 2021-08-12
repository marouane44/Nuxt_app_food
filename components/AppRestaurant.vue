<template>
 <section class="restaurantinfo">
<div v-for="store in fooddata " :key="store.id">
<h2>{{store.name}}</h2>
<p> deliveryTime :{{store.deliveryTime}}</p>
<p>{{store.rating}}</p>
<p v-if="store.freeDelivery" class="label">
    <span>
        Free Delivery
    </span>
</p>
<div class="row">
<div
     v-for="menuitemm in store.menu" 
     :key="menuitemm.id"
     class="items"
     :style="`background : url(${menuitemm.img}) no-repeat center center`">

<div class="iteminfo" >
<div>
    <h4>{{menuitemm.item}} </h4>
    <p>{{priceFormatting(menuitemm.price)}} </p>
 
</div>
<button class="ghost">View Item</button>
</div>


</div>
</div>
</div>
 </section>
</template>

<script>
  import { mapState } from 'vuex';
  
  export default {
      computed: {
          ...mapState([
              'fooddata',
          ])
      },
      methods
    :{
        priceFormatting(item){
            return '$' +item.toFixed(2);
        }
    }
  };
</script>

<style lang="scss" scoped>

</style>