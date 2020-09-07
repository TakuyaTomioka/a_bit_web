<template>
  <div class="mv">
    <img src="@/assets/img/mv.jpg" class="isPC pc" alt="メインビジュアル">
    <img src="@/assets/img/mv_sp.jpg" class="isSP sp" alt="スマホ用メインビジュアル">
    <p class="message isPC">明日の開発を<br><span class="orange">ちょっと</span>良くする</p>
    <p class="message isSP">明日の開発を<br><span class="orange">ちょっと</span><br>良くする</p>
  </div>
</template>

<script>
export default {
  
}
</script>
<style>
.mv{
  font-family: 'Kosugi Maru', sans-serif;
  position: relative;
  width: 100%;
}


.isPC{
  display: block;
}
.isSP{
  display: none;
}
.message{
  font-size: 4.0rem;
  position: absolute;
  top: 50%;
  left: 30%;
  -ms-transform: translate(-50%,-50%);
  -webkit-transform: translate(-50%,-50%);
  transform: translate(-50%,-50%);
  margin:0;
  padding:0;
}
.orange{
  color: #DB7443;
}
@media screen and (max-width: 768px){
  .sp{
    height: 90vh;
    width: 100%;
  }
  .isPC{
    display: none;
  }
  .isSP{
    display: block;
  }
  .message{
    font-size: 2.4rem;
    top: 50%;
    left: 38%;
    /* width: 100%; */
  }
  span{
    font-size: 3.0rem;
  }
}
</style>