<template>
<div class="bg-blue">
  <nav>
    <div class="logo">
      <nuxt-link to="/"><img src="@/assets/img/logo_web2.svg" alt="ロゴ"></nuxt-link>
    </div>
    <div class="hamburger" @click="toggleActive">
      <div v-if="isActive === false">
        <div class="line"></div>
        <div class="line"></div>
        <div class="line"></div>
      </div>
      <div class="toggle" v-if="isActive === true">
       <img src="@/assets/img/clear.svg" alt="Cancel" class="cancel">
      </div>
    </div>
    <ul class="nav-links isPC">
      <li><nuxt-link to="/categories">技術記事</nuxt-link></li>
      <li><nuxt-link to="portofolio">ポートフォリオ</nuxt-link></li>
      <li><nuxt-link to="contact">お問い合わせ</nuxt-link></li>
    </ul>
    <transition class="isSP">
      <ul class="nav-links" v-show="show">
        <li><nuxt-link to="/categories">技術記事</nuxt-link></li>
        <li><nuxt-link to="portofolio">ポートフォリオ</nuxt-link></li>
        <li><nuxt-link to="contact">お問い合わせ</nuxt-link></li>
      </ul>
    </transition>
  </nav>
</div>
</template>

<script>

export default {
  data() {
    return{
      show: false,
      isActive: false,
    }
  },
  methods:{
    toggleActive: function(){
      this.show = !this.show;
      this.isActive = !this.isActive;
    }
  }
}
</script>

<style scoped>
.isPC{
  display: block;
}
.isSP{
  display: none;
}
.logo{
  max-width: 350px;
  width: 20vw;
  margin-left: 5vw;
  z-index: 1;
}
.bg-blue{
  background: #B4DAED;
}

nav {
  max-width: 1980px;
  margin: 0 auto;
  display: flex;
  height: 10vh;
  align-items: center;
  font-family: 'Kosugi Maru', sans-serif;
}

.nav-links {
  display: flex;
  list-style: none;
  width: 50%;
  height: 100%;
  justify-content: space-around;
  align-items: center;
  margin-left: auto;
}

.nav-links li a {
  color: white;
  text-decoration: none;
  font-size: 24px;
  font-weight: 700;
}

@media screen and (max-width: 768px) {
  .isPC{
    display: none;
  }
  .isSP{
    display: block;
  }
  .logo{
    width: 40vw;
  }
  .cancel{
    width: 12vw;
  }

  .line {
    width: 30px;
    height: 3px;
    background: white;
    margin: 5px;
  }
  nav {
    display: block;
    position: relative;
  }

  .hamburger {
    position: absolute;
    cursor: pointer;
    right: 5%;
    top: 50%;
    transform: translate(-5%, -50%);
    z-index: 2;
  }

  .nav-links {
    position: fixed;
    background: #B4DAED;
    height: 100vh;
    width: 100%;
    flex-direction: column;
    clip-path: circle(800px at 90% -10%);
    -webkit-clip-path: circle(800px at 90% -10%);
    transition: all 1s ease-out;
  }

  .nav-links li a {
    color: white;
    text-decoration: none;
    font-size: 24px;
    font-weight: 700;
  }

  .nav-links li:nth-child(3){
    margin-bottom:100px;
  }


  .v-enter-active {
    transition: all 1.0s ease 0s;
  }
  .v-leave-active {
    transition: all 0.3s ease 0s;
  }
  .v-leave-active {
    position: absolute;
  }
  .v-enter,
  .v-leave-to {
    opacity: 0;
  }
  .v-enter {
    transform: translateX(60px);
  }
  .v-enter-to,
  .v-leave {
    transform: translateX(0);
  }
  .v-leave-to {
    transform: translateX(-60px);
  }

}
</style>