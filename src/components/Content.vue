<script setup>
import Product from "./Product.vue";
import Sallers from "./Sallers.vue";
import Informations from "./Informations.vue";
import Experts from "./Experts.vue";

defineProps({
  view: Array,
});
</script>
<template>
  <div class="block">
    <!-- <transition name="fade"> -->
    <Product v-if="view.indexOf('product') !== -1" :view="view" />
    <!-- </transition> -->
    <!-- <transition name="fade"> -->
    <Sallers v-if="view.indexOf('sallers') !== -1" />
    <!-- </transition> -->
  </div>
  <div class="block">
    <!-- <transition name="fade"> -->
    <Informations v-if="view.indexOf('information') !== -1" :view="view" />
    <!-- </transition> -->
    <!-- <transition name="fade"> -->
    <Experts v-if="view.indexOf('experts') !== -1" />
    <!-- </transition> -->
  </div>
</template>
<style scoped lang="scss">
.block {
  display: flex;
  gap: 38px;
  width: 100%;
}

// .fade-enter-active,
// .fade-leave-active {
//   transition: opacity 0.1s ease;
// }

// .fade-enter-from,
// .fade-leave-to {
//   opacity: 0;
// }
</style>
