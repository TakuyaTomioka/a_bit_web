<template>
  <nav>
    <div class="logo">
      <img src="@/assets/img/logo_web2.svg" alt="ロゴ">
    </div>
    <div>
      <ul class="menu">
        <li>ブログ</li>
        <li>ポートフォリオ</li>
        <li>お問い合わせ</li>
      </ul>
    </div>
  </nav>
</template>

<style scoped>
nav{
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: .8vh 5vw;
}

.logo{
  width: 20vw;
}

.menu{
  display: flex;
}

.menu ul{
  display: flex;
  justify-content: space-evenly;
}

.menu li{
  margin-right: 2vw;
  font-size: 18px;
}
@media screen and (max-width:767px) {

nav{
  padding: 3vh 5vw;
}

.logo{
  width: 40vw;
}

.menu{
  display: none;
}

.menu li{
  font-size: 0.8em;
}
}
</style>