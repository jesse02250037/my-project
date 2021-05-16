<template>
  <div id="home">
    <nav-bar class="home-nav">
      <template v-slot:center>首页</template>
    </nav-bar>
    <!-- 首页的轮播图 -->
    <home-swiper :banners='banners'></home-swiper>
    <!-- 推荐 -->
    <home-recommends :recommends='recommends'></home-recommends>
    <!-- 首页中间图片 -->
    <home-feature></home-feature>
  </div>
</template>

<script>
import NavBar from "components/common/navbar/NavBar";
import HomeSwiper from './childcpms/HomeSwiper'
import HomeRecommends from './childcpms/HomeRecommends'
import HomeFeature from './childcpms/HomeFeature'
import { getHomeMultidata } from "network/home";

export default {
  name: "Home",
  data() {
    return {
      banners: [],
      recommends: [],
    };
  },
  components: {
    NavBar,
    HomeSwiper,
    HomeRecommends,
    HomeFeature
  },
  created() {
    getHomeMultidata().then((res) => {
      // 打印数据
      console.log(res);
      this.banners = res.data.banner.list;
      this.recommends = res.data.recommend.list;
    });
  },
};
</script>


<style scoped>
.home-nav {
  background-color: #ff8198;
  color: #fff;
  position: fixed;
  left: 0;
  right: 0;
  top: 0;
  z-index: 999;
}

</style>
