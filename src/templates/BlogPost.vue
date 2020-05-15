<template>
  <Layout>
    <Section container="md" dots="true" >

      <div class="post-header container-md text-center mb-x2">
        <h1 v-html="$page.post.title"/>
      </div>

      <div class="post-content post mb-x2">

        <p class="lead" v-html="$page.post.excerpt"/>

        <p class="lead" v-html="$page.post.content"/>
        <a :href="$page.post.path">Link</a>
      </div>

    </Section>
  </Layout>
</template>

<page-query>
query ($id: ID!) {
  post: blogPost (id: $id) {
    title
    excerpt
    content
    path
  }
}
</page-query>

<script>
export default {}
</script>