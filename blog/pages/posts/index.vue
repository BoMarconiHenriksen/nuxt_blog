<template>
    <div class="posts-page">
        <PostList :posts="loadedPosts"/>
    </div>
</template>

<script>
import PostList from '@/components/Posts/PostList'

export default {
    components: {
        PostList
    },
    // Return the page after it has fetched the data from a server.
    asyncData(context, callback) {
        setTimeout(() => {
        callback(null, {
            loadedPosts: [
            {
            id: '1', 
            title: 'Our First Post', 
            previewText: 'This is our first post!', 
            thumbnailLink: 'https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80'
            },
            {
            id: '2', 
            title: 'Our Second Post', 
            previewText: 'This is our second post!', 
            thumbnailLink: 'https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80'
            }
            ]
        });
        }, 1500);
    },    
}
</script>


<style scoped>
.posts-page {
    display: flex;
    justify-content: center;
    align-items: center;
}

</style>

