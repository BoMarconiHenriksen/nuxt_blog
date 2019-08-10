

<template>
    <section class="post-list">
        <PostPreview
        v-for="post in posts"
        :key="post.id"
        :id="post.id"
        :is-admin="isAdmin" 
        :thumbnail="post.thumbnailLink"
        :title="post.title"
        :previewText="post.previewText"/>
    </section>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview';

export default {
  components: {
    // https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    },
    posts: {
      type: Array,
      required: true
    }
  },
  
}
</script>

<style scoped>
.post-list {
    display: flex;
    padding: 20px;
    box-sizing: border-box;
    flex-wrap: wrap;
    align-items: center;
    justify-content: center;
}
</style>
