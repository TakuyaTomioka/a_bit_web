<template>
  <div>
    <Hero />
    <div class="wrapper">
      <h1>記事一覧</h1>
      <Card 
        v-for = "post in posts"
        :key = "post.sys.id"
        :image = "post.fields.headerImage.fields.file.url"
        :slug = "post.fields.slug"
        :title = "post.fields.title"
        :summary = "post.fields.summary"
        :date = "post.fields.publishedAt"
      />
    </div>
  </div>
</template>

<script>
import client from '@/plugins/contentful'
import Hero from'@/components/VisualComponents/Hero'
import Card from '@/components/VisualComponents/Card'
export default {
  asyncData() {
  return Promise.all([
    client.getEntries({
      'content_type': 'blogPost',
      order: '-sys.createdAt',
      'fields.recommendation': false,
      limit: 10
    })
  ])
  .then(([posts]) => {
    return {
      posts: posts.items
    }
  })
  .catch(e => console.log(e));
  },
  components:{
    Hero,
    Card,
  }
}
</script>

<style scoped>

h1{
  font-size: 1.8rem;
  font-family: 'Roboto Mono', sans-serif;
  width: 15%;
  padding:0 0 .1rem .7rem;
  border-bottom: solid #E5E5E5 5px;
}
.wrapper{
  max-width: 1980px;
  margin: 0 auto;
}

@media screen and (max-width: 768px){
  h1{
    width: 50%;
  }
  .wrapper{
    margin: 1.0rem;
  }
}
</style>
