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
    <div class="updates">
      <div class="container">
        <h2>Nunca perca um post. Registre-se agora para ter uma conta grátis!</h2>
        <router-link class="router-button" to="#">Registre-se em Geek Blog <Arrow class="arrow arrow-light"/></router-link>
      </div>
    </div>
  </div>
</template>

<script>
import BlogPost from "../components/BlogPost";
import BlogCard from "../components/BlogCard";
import Arrow from "../assets/Icons/arrow-right-light.svg";

export default {
  name: "Home",
  components: { BlogPost, BlogCard, Arrow },
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

.updates {
  .container {
    padding: 100px 25px;
    display: flex;
    flex-direction: column;
    align-items: center;

    @media(min-width: 800px) {
      padding: 125px 25px;
      flex-direction: row;
    }

    .router-button {
      display: flex;
      font-size: 14px;
      text-decoration: none;

      @media(min-width: 800px) {
        margin-left: auto;
      }
    }

    h2 {
      font-weight: 300;
      font-size: 32px;
      max-width: 425px;
      width: 100%;
      text-align: center;
      text-transform: uppercase;

      @media(min-width: 800px) {
        text-align: initial;
        font-size: 40px;
      }
    }
  }
}
</style>
