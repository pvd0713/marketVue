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
    <Product v-if="view.indexOf('product') !== -1" />
    <Sallers v-if="view.indexOf('sallers') !== -1" />
  </div>
  <div class="block">
    <Informations v-if="view.indexOf('information') !== -1" :view="view"/>
    <Experts v-if="view.indexOf('experts') !== -1" />
  </div>
</template>
<style scoped lang="scss">
.block {
  display: flex;
  gap: 38px;
  width: 100%;
}
</style>
