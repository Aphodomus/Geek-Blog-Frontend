<template>
  <div class="home">
    <BlogPost :post="welcomeScreen" />
    <BlogPost :post="post" v-for="(post, index) in sampleBlogPost" :key="index" />
    <div class="blog-card-wrap">
      <div class="container">
        <h3>Últimos posts</h3>
        <div class="blog-cards">
          <BlogCard :post="post" v-for="(post, index) in sampleBlogCards" :key="index" />
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import BlogPost from "../components/BlogPost";
import BlogCard from "../components/BlogCard";

export default {
  name: "Home",
  components: { BlogPost, BlogCard },
  data() {
    return {
      welcomeScreen: {
        title: "Bem Vindo!",
        blogPost: "Acesse nosso site semanalmente para ter acesso a conteúdos de jogos, animes, mangás e muito mais! Venha fazer parte desta comunidade.",
        welcomeScreen: true,
        photo: "games",
      },
      sampleBlogPost: [
        {
          title: "This is a Filter Title!",
          blogHTML: "This is a filter blog post title!",
          blogCoverPhoto: "space",
        },
        {
          title: "This is a Filter Title2!",
          blogHTML: "This is a filter blog post title!",
          blogCoverPhoto: "anime",
        },
      ],
      sampleBlogCards: [
        { blogTitle: "Blog Card #1", blogCoverPhoto: "stock-1", blogDate: "May 1, 2021" },
        { blogTitle: "Blog Card #2", blogCoverPhoto: "stock-2", blogDate: "May 5, 2020" },
        { blogTitle: "Blog Card #3", blogCoverPhoto: "stock-3", blogDate: "May 9, 2019" },
        { blogTitle: "Blog Card #4", blogCoverPhoto: "stock-4", blogDate: "May 2, 2021" },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
.blog-card-wrap {
  h3 {
    font-weight: 300;
    font-size: 28px;
    margin-bottom: 32px;
  }
}
</style>
