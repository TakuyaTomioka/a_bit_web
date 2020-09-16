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
        :date = "post.fields.publishedAt"
        :recommendation = "post.fields.recommendation"
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
    return client
    .getEntries({
      content_type: 'blogPost',
      order: '-fields.publishedAt',
      limit: 10
    })
    .then(results => {
      return { posts: results.items }
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
  margin: 1.4rem 0;
  width: 15%;
  padding:0 0 .1rem .7rem;
  border-bottom: solid #E5E5E5 5px;
}

@media screen and (max-width: 768px){
  h1{
    margin: 1.0rem;
    width: 50%;
  }
}
</style>
