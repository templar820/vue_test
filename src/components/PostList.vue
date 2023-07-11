<template>
  <div>
    <h3>Список постов</h3>
  </div>
  <post-item
    v-for="post in posts"
    :post="post"
  />
</template>

<script>
import PostItem from "@/components/PostItem.vue";

export default {
  components: {PostItem},
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
