<template>
  <img alt="Vue logo" src="./assets/logo.png" />
  <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
  <div id="app">
    <PostForm @add-post="addPost" />
    <PostList
      :posts="posts"
      @like-post="likePost"
      @comment-post="commentPost"
      @delete-post="deletePost"
    />
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import PostForm from "./components/PostFrom.vue";
import PostList from "./components/PostList.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    PostForm,
    PostList,
  },
  data() {
    return {
      posts: [],
    };
  },
  methods: {
    addPost(newPost) {
      this.posts.push(newPost);
    },
    likePost(index) {
      this.posts[index].likes++;
    },
    commentPost({ index, comment }) {
      this.posts[index].comments.push(comment);
    },
    deletePost(index) {
      this.posts.splice(index, 1);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
