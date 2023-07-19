<template>
  <form @submit.prevent @submit="createPost">
    <h4>Create post</h4>

    <MyButton>create</MyButton>
  </form>
</template>

<script lang="ts">
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
  emits:{
    createPost(payload: { title: string, description: string, id: any }) {
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
    createPost() {
      // this.post.id = new Date().getSeconds();
      // this.$emit("createPost", this.post)
      // this.post = {
      //   title: "",
      //   description: ""
      // }
    },
  }
}
</script>

<style lang="scss" scoped>

</style>
