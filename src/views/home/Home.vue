<template>
  <div id="home">
    <nav-bar class="home-nav">
      <div slot="center">购物街</div>
    </nav-bar>
    <home-swiper :cbanners="banners"/>
    <recommend-view :recommends="recommends"/>
    <FeatureView/>
    <tab-control class="tab-control" :titles="['流行', '新款', '精选']"/>
    <good-list :goods="goods['pop'].list"/>
  </div>
</template>

<script>

  import HomeSwiper from "./childComps/HomeSwiper";
  import RecommendView from "./childComps/RecommendView";
  import FeatureView from "./childComps/FeatureView";

  import NavBar from 'components/common/navbar/NavBar';
  import TabControl from 'components/content/tabControl/TabControl';
  import GoodList from 'components/content/goods/GoodsList'

  import {getHomeMultidata, getHomeGoods} from "network/home";

  export default {
    name: "home",
    components: {
      HomeSwiper,
      RecommendView,
      FeatureView,
      NavBar,
      TabControl,
      GoodList
    },
    data() {
      return {
        banners: [],
        recommends: [],
        goods: {
          'pop': {page: 0, list: []},
          'new': {page: 0, list: []},
          'sell': {page: 0, list: []},
        }
      }
    },
    created() {
      // 1.请求多个数据
      this.getHomeMultidata()

      // 2.请求商品数据
      this.getHomeGoods('pop')
      this.getHomeGoods('new')
      this.getHomeGoods('sell')
    },
    methods: {
      getHomeMultidata() {
        getHomeMultidata().then(res => {
          this.banners = res.data.banner.list
          this.recommends = res.data.recommend.list
          // console.log(res);
        })
      },
      getHomeGoods(type) {
        const page = this.goods[type].page + 1
        getHomeGoods(type, page).then(res => {
          this.goods[type].list.push(...res.data.list)
          this.goods[type].page += 1
          // console.log(res);
        })
      }
    }
  }
</script>

<style scoped>
  #home {
    padding-top: 30px;
  }

  .home-nav {
    height: 30px;
    background-color: var(--color-tint);
    color: white;

    position: fixed;
    right: 0;
    left: 0;
    top: 0;
    z-index: 9;
  }

  .tab-control {
    position: sticky;
    top: 30px;
    z-index: 9;
  }
</style>
