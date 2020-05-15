<template>
  <Layout>
     <Section container="md" class="blog-posts">
      <div class="mb-x2 container-sm text-center">
        <h1>Gridsome Blog</h1>
      </div>
      <div v-for="edge in $page.posts.edges" :key="edge.node.id" :post="edge.node">
        <div>
          {{edge.node.title}}
          <a :href="edge.node.path">Link</a>
        </div>
      </div>

    </Section>
  </Layout>
</template>

<page-query>
query {
  posts: allBlogPost {
    edges {
      node {
        id
        title
        path
        excerpt
        content
      }
    }
  }
}
</page-query>

<script>

export default {
  metaInfo: {
    title: 'Blog'
  }
}
</script>
