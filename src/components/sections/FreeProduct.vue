<template>
  <div class="free-product">
    <div class="container">
      <div class="wrap" v-if="isDesktop">
        <CardProduct
          v-for="(product, index) in productsList"
          :key="index"
          :product="product"
        />
      </div>
      <div class="title aos" data-aos="flip-left">
        零成本快速展示您的空间设计
      </div>
      <div class="sub-title">知了云展轻松呈现逼真的三维漫游效果</div>
    </div>
  </div>
</template>
<script>
import breakpointMixin from "../../mixins/breakpoint";
import { freeProducts } from "../../_mock_";
import CardProduct from "../cards/CardProduct.vue";
export default {
  mixins: [breakpointMixin],
  components: {
    CardProduct,
  },
  computed: {
    productsList() {
      return freeProducts;
    },
  },
};
</script>
<style lang="scss" scoped>
@import url("../../assets/css/sections/free-product.scss");
</style>
