<template>
<div class="goodslist">
  <goods-list-item v-for="item in goods" :key="item" :goodsItem='item' class="goods-list-item"></goods-list-item>
</div>
</template>

<script>
import GoodsListItem from "./GoodsListItem";
export default {
  name: "GoodsList",
  props: {
    goods: {
      type: Array,
      default() {
        return [];
      },
    },
  },
  components: {
    GoodsListItem,
  },
};
</script>

<style scoped>
.goodslist{
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.goods-list-item{
  width: 48%;
}
</style>
