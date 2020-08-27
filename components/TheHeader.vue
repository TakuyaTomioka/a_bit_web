<template>
  <div>
    <header>
      <Nav />
    </header>
    <Hamburger />
  </div>
</template>

<script>
import Nav from '@/components/HeaderComponents/Nav';
import Hamburger from '@/components/HeaderComponents/Hamburger';
export default {
  components:{
    Nav,
    Hamburger,
  }
}
</script>

<style>
  
</style>