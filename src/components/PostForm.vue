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

<script>
export default {
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
      this.$emit("create", this.post, "laslals")
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
