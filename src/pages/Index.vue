<template>
  <Layout>

  <div class="mb-2 text-center">
    <b-avatar src="https://i.ibb.co/5XDkhP3/actros-avatar.jpg" size="6rem"></b-avatar>
  </div>    

    <g-link
      :to="post.node.path"
      v-for="post in $page.posts.edges"
      :key="post.node.id"
      class="blog-post"
    >

    <div class="media my-2">
      <div class="media-body">
          <b>{{ post.node.title }}</b>
        </h3>
      </div>
    </div>

    </g-link>
  <blockquote class="blockquote">

  
  </blockquote>

  </Layout>
</template>

<page-query>
query Blog {
  posts: allBlogPost(sortBy: "date") {
    edges {
      node {
        id
        path
        date                
        title
        excerpt
        image
      }
    }
  }
}
</page-query>

<style lang="scss" scoped>

.media-body {
  padding: 2px 16px;
  background-color: white;
  border-radius: 5px;
  background-color: #1e1e1e
}


</style>

