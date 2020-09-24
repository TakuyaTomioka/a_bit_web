<template>
  <div>
    <Hamburger />
  </div> 
</template>

<script>
import Hamburger from '@/components/HeaderComponents/Hamburger';
export default {
  components:{
    Hamburger,
  }
}
</script>

<style scoped>
  div{
    position: fixed;
    z-index: 2;
    width: 100%;
  }
</style>