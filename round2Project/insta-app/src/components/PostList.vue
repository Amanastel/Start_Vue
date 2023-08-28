<template>
    <div class="post-list">
      <h2>Posts</h2>
      <div v-for="post in localPosts" :key="post.id" class="post">
        <h3>{{ post.username }}</h3>
        <p>{{ post.caption }}</p>
        <p>{{ post.likes }} likes</p>
        <button @click="likePost(post.id)">Like</button>
  
        <ul>
          <li v-for="(comment, commentIndex) in post.comments" :key="commentIndex">
            {{ comment }}
          </li>
        </ul>
        <form @submit.prevent="submitComment(post.id)">
          <input type="text" v-model="comment" placeholder="Enter comment" required>
          <button type="submit">comment</button>
        </form>
  
        <button @click="deletePost(post.id)">Delete</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    name: "PostList",
    props: ["posts"],
    data() {
      return {
        localPosts: [...this.posts],
        comment: ""
      };
    },
    methods: {
      likePost(postId) {
        const index = this.localPosts.findIndex(post => post.id === postId);
        if (index !== -1) {
          this.$emit("like-post", index);
        }
      },
      submitComment(postId) {
        if (this.comment) {
          const index = this.localPosts.findIndex(post => post.id === postId);
          if (index !== -1) {
            this.$emit("comment-post", { index, comment: this.comment });
            this.comment = "";
          }
        } else {
          alert("Please fill in comment");
        }
      },
      deletePost(postId) {
        const index = this.localPosts.findIndex(post => post.id === postId);
        if (index !== -1) {
          this.$emit("delete-post", index);
        }
      }
    }
  };
  </script>
  
  <style scoped>
  /* Your styling here */
  </style>
  



<style scoped>  
#post_form input[type=text], #post_form textarea {
    width: 100%;
    padding: 12px 20px;
    margin: 8px 0;
    box-sizing: border-box;
}
#post_form button {
    background-color: #4CAF50;
    color: white;
    padding: 14px 20px;
    margin: 8px 0;
    border: none;
    cursor: pointer;
}
#post_form button:hover {
    opacity: 0.8;
}
#post_form {
    border-radius: 5px;
    background-color: #f2f2f2;
    padding: 20px;
}

</style>