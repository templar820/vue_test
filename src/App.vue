<template>
  <div class="app">
    <PostForm

    />
    <PostList v-bind:posts="posts"/>
  </div>
</template>
<script>
import PostList from "@/components/PostList.vue";
import PostForm from "@/components/PostForm.vue";

export default {
  components: {
    PostList,
    PostForm,
  },
  data() {
    return {
      posts: [
        {id: 1, title: "Title1", description: "Description1"},
        {id: 2, title: "Title2", description: "Description2"},
        {id: 3, title: "Title3", description: "Description3"},
        {id: 4, title: "Title4", description: "Description4"},
      ],
      title: "",
      description: "",
    }
  },

  methods: {
    createPost(post, desc){
      this.posts.push(post);
    }
  }

}
</script>
<style>
* {
  margin: 0;
  box-sizing: border-box;
  padding: 0px;
}


.app {
  padding: 20px;
}

.app form {
  display: flex;
  justify-content: center;
  flex-direction: column;
  align-content: center;
  gap: 16px;
}

.app input {
  width: 100%;

}
</style>
