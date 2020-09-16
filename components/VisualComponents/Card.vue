<template>
  <section id="latest">
    <div class="posts" v-if="recommendation === false">
      <nuxt-link :to="{ slug }">
        <img :src="image" alt="thumbnail">
        <div class="post-overview">
          <h2 class="post-title">{{ title }}</h2>
          <time class="post-date">{{ date }}</time>
        </div>
      </nuxt-link>
    </div>
  </section>
</template>

<script>
export default {
  props:{
    title: {
      type: String,
      default: ''
    },
    date: {
      type: String,
      default: ''
    },
    image: {
      type: String,
      default: ''
    },
    slug: {
      type: String,
      default: ''
    },
    recommendation:{
      type: Boolean,
      default: false
    }
  }
}
</script>

<style scoped>

h1{
  font-size: 1.8rem;
  font-family: 'Roboto Mono', sans-serif;
  margin: 1.4rem 0;
  width: 15%;
  padding:0 0 .1rem .7rem;
  border-bottom: solid #E5E5E5 5px;
}

img{
  width: 20%;
  height: auto;
  object-fit: cover;
}

.posts{
  margin: 1.3rem 0;
  border-bottom: #eee solid 1px;
  min-height: 200px;
}

div a{
  display: flex;
  text-decoration: none;
  color: black;
}

.post-overview{
  padding-left: 20px;
}
.post-title{
  font-family: 'Roboto Mono','Kosugi Maru', sans-serif;
  padding-top: 10px;
  /* font-size: 1.2rem; */
}

.post-date{
 padding-top: 100px;
 font-size: 0.8rem;
}

.wrapper{
  max-width: 1280px;
  width: 80%;
  margin: 0 auto;
}

@media screen and (max-width: 768px){
  h1{
    margin: 1.0rem;
    width: 50%;
  }
  img{
    width: 100px;
    height: 100px;
  }

  .post-title{
    font-size: 0.9rem;
  }

  .post-date{
    padding-top: 20px;
    font-size: 0.8rem;
  }

  .posts{
    margin: 1rem 0;
    min-height: 100px;
  }
  .wrapper{
    width: 90%;
  }

}
</style>