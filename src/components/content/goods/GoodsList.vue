<template>
    <div class="goods">
      <good-list-item v-for="item in goods" :goods-item="item"/>
      {{}}
    </div>
</template>

<script>
  import GoodListItem from './GoodListItem'

  export default {
    name: "goods-list",
    components: {
      GoodListItem
    },
    props: {
      goods: {
        type: Array,
        default() {
          return []
        }
      }
    }
  }
</script>

<style scoped>
  .goods {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    padding: 2px;
  }

</style>
