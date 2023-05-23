<template>
  <form @submit.prevent @submit="createPost">
    <h4>Create post</h4>
    <input
      v-model="post.title"
      placeholder="title"
    />
    <input
      v-model="post.description"
      placeholder="description"
    />
    <button>create</button>
  </form>
</template>

<script lang="ts">
export default {
  emits:{
    createPost(payload: { title: string, description: string }) {
      // мидлваря получается
      console.log(payload);
    }
  },
  data() {
    return {
      post: {
        title: "",
        description: "",
      }
    }
  },
  methods: {
    createPost(event) {
      this.post.id = new Date().getSeconds();
      this.$emit("createPost", this.post)
      this.post = {
        title: "",
        description: ""
      }
    },
  }
}
</script>

<style lang="scss" scoped>

</style>
