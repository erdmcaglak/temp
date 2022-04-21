<template>
  <div class="main">
    <Images/>
    <!-- <Card/> -->
  </div>
</template>

<script>
import Images from "@/components/images.vue"
import Card from "@/components/card.vue"
export default {
  components:{
    Images,
    Card
  }
}
</script>

<style lang="scss">
html,body{
  height: 100%;
}
.main{
  height: 100%;
}
</style>