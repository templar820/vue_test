<template>
  <div class="post" v-for="post in posts">
    <strong>ID:</strong> {{ post.id }}
    <strong>Название:</strong> {{ post.title }}
    <strong>Описание:</strong> {{ post.description }}
  </div>
</template>

<script>
export default {
  props: {
    posts: {
      type: Array,
      required: true
    }
  },
  setup() {
    return {}
  }
}
</script>

<style lang="scss" scoped>
.post {
  border: 2px solid green;
  margin: 15px 0px;
}
</style>
