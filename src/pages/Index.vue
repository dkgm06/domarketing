<template>
  <Layout>
    <div>

    <!-- Learn how to use images here: https://gridsome.org/docs/images -->
    <g-image class="main-image" alt="Example image" src="~/images/womanred.jpg" />
    
    <h1>Bonjour! Hola! Hello! </h1>
    <p>Lets talk about money making</p>
    </div>
    <section class="posts">
    <PostList v-for="edge in $page.allPost.edges" :key="edge.node.id" :post="edge.node" />
  </section>
  </Layout>
</template>

<page-query>
query {
  allPost {
    totalCount
    edges {
      node {
        id
        title
        timeToRead
        description
        path
      }
    }
  }
}
</page-query>

<script>
export default {
  metaInfo: {
    title: 'Hello, world!'
  }
}
</script>

<style>
body {
  background: #ccc;
  margin: 0;
  padding: 0;
}
.main-image {
  width: 100%;
  margin: 0;
  padding: 0;
}
.home-links a {
  margin-right: 1rem;
}
</style>
