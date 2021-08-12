<template>
<main class="container">

<AppHeader/>
<AppRestaurant/>
</main>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue';
import AppRestaurant from '@/components/AppRestaurant.vue';
export default {
  components: {
    AppHeader,
    AppRestaurant,
  },
};

</script>
