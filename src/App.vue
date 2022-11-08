<script>
import AppHeader from "./components/AppHeader.vue";
import ProductsList from "./components/ProductsList.vue";
import AppFooter from "./components/AppFooter.vue";

export default {
  components: {
    AppHeader,
    ProductsList,
    AppFooter
  }
}
</script>

<template>
  <AppHeader />
  <ProductsList />
  <AppFooter />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
</style>