<template>
  <div class="mv">
    <div class="filter">
      <img src="@/assets/img/mv.jpg" class="isPC pc" alt="メインビジュアル">
      <img src="@/assets/img/mv_sp.jpg" class="isSP sp" alt="スマホ用メインビジュアル">
    </div>
    <p class="message isPC">明日のWEBを<br><span class="orange">ちょっと</span>良くする</p>
    <p class="message isSP">明日のWEBを<br><span class="orange">ちょっと</span><br>良くする</p>
  </div>
</template>

<script>
export default {
  
}
</script>
<style>
.mv{
  /* font-family: 'Kosugi Maru','Roboto', sans-serif; */
  font-family: 'Roboto', 'Kosugi Maru', sans-serif;
  position: relative;
  max-width: 1980px;
  width: 100%;
  margin: 0 auto;
}
img{
  opacity: 0.8;
}
.filter{
  background-color: rgb(202, 191, 191);
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
    left: 34%;
    /* width: 100%; */
  }
  span{
    font-size: 3.0rem;
  }
}
</style>