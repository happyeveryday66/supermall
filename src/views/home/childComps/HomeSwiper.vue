<template>
  <div>
    <swiper class="home-swiper">
      <swiper-item v-for="item in cbanners" :key="item.background">
        <a :href="item.link">
          <img :src="item.image" alt="" @load="imageLoad">
        </a>
      </swiper-item>
    </swiper>
  </div>
</template>

<script>
  import {Swiper, SwiperItem} from 'components/common/swiper';
  export default {
    name: "HomeSwiper",
    props: {
      cbanners:{
        type:Array,
        default() {
            return []
        }
      }
    },
    data() {
      return {
        isLoad: false
      }
    },
    components:{
      Swiper,
      SwiperItem
    },
    methods: {
      imageLoad() {
        if (!this.isLoad) {
          this.$emit('swiperImageLoad')
          this.isLoad = true
        }
        
      }
    }
  }
</script>

<style scoped>


</style>
