<template>
  <div>
      <h2>外卖详情</h2>
      <p>name:{{foodDetail.name}}</p>
      <p>{{foodDetail.price}}</p>
  </div>
</template>

<script>
import {mapGetters,mapActions} from "vuex"
export default {
    computed:{
        ...mapGetters({
            "foodDetail":"foodDetail"
        })
    },
    methods:{
        ...mapActions({
            "requestFoodDetail":"requestFoodDetail"
        })
    },
    mounted(){
      var foodId=this.$route.query.foodId
        this.requestFoodDetail(foodId)
    }
}
</script>

<style>

</style>