<template>
  <div class="home">
    <UpperBanner />
    <TheFeatures />
    <TopOffers />
    <FlashDealsSwiper :products="FlashDealsSwiper" />
    <TopCategory />
    <NewProducts :products="newProducts" />
    <QualityFeatures />
  </div>
</template>

<script>
import UpperBanner from "@/components/Home-page/UpperBanner";
import TopOffers from "@/components/Home-page/TopOffers";
import TheFeatures from "@/components/Home-page/TheFeatures";
import FlashDealsSwiper from "@/components/Home-page/FlashDealsSwiper";
import TopCategory from "@/components/Home-page/TopCategory";
import NewProducts from "@/components/Home-page/NewProducts";
import QualityFeatures from "@/components/Home-page/QualityFeatures";

import { productsModule } from "@/stores/products";
import { mapActions, mapState } from "pinia";

export default {
  name: "HomeView",
  components: {
    UpperBanner,
    TopOffers,
    TheFeatures,
    FlashDealsSwiper,
    TopCategory,
    NewProducts,
    QualityFeatures,
  },
  computed: {
    ...mapState(productsModule, ["FlashDealsSwiper", "newProducts"]),
  },
  methods: {
    ...mapActions(productsModule, ["getProducts"]),
  },
  async mounted() {
    await this.getProducts();
  },
};
</script>
