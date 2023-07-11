<template>
  <div class="post">
    <strong>ID:</strong> {{ post.id }}
    <strong>Название:</strong> {{ post.title }}
    <strong>Описание:</strong> {{ post.description }}
    <MyButton style="align-self: auto">Delete</MyButton>
  </div>
</template>

<script>
import MyButton from "@/components/UI/MyButton.vue";

export default {
  components: {MyButton},
  props: {
    post: {
      type: Object,
      required: true,
    }
  },
  setup() {


    return {}
  }
}
</script>

<style lang="scss" scoped>

</style>
