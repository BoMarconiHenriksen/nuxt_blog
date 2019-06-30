

<template>
    <section class="post-list">
        <PostPreview
        id="1"
        :is-admin="isAdmin" 
        thumbnail="https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
        title="Hello There!"
        previewText="This is my secound post"/>

        <PostPreview 
        id="2"
        :is-admin="isAdmin"
        thumbnail="https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
        title="Hello There again!"
        previewText="This is my first post"/>

        <PostPreview 
        id="3"
        :is-admin="isAdmin"
        thumbnail="https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80"
        title="Hello There one more time!"
        previewText="This is my third post"/>
      
    </section>
</template>

<script>
import PostPreview from '@/components/Posts/PostPreview';

export default {
  components: {
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
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
