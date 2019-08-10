<template>
    <div class="single-post-page">
        <section class="post">
            <h1 class="post-title">{{ loadedPost.title }}</h1>
            <div class="post-details">
                <div class="post-detail">Last updated on {{ loadedPost.updatedDate }}</div>
                <div class="post-detail">Written by {{ loadedPost.author }}</div>
            </div>
            <p class="post-content">{{ loadedPost.content }}</p>
        </section>
        <section class="post-feedback">
            <p>Let me know whatyou think of the post, send a mail to <a href="mailto:feedback@domain.com">feedback@domain.com</a></p>
        </section>
    </div>
</template>

<script>
export default {
  // Return the page after it has fetched the data from a server.
    asyncData(context, callback) {
        setTimeout(() => {
        callback(null, {
            loadedPost: 
            {
            id: '1', 
            title: 'Our First Post (ID: ' + context.params.id + ')' , 
            previewText: 'This is our first post!', 
            author: 'Bob Samson',
            updatedDate: new Date(),
            content: 'Dummy text which is not the preview text!!!',
            thumbnailLink: 'https://images.unsplash.com/photo-1556740714-a8395b3bf30f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=1350&q=80'
            }
        });
        }, 1500);
    },      
}
</script>


<style scoped>
.single-post-page {
  padding: 30px;
  text-align: center;
  box-sizing: border-box;
}

.post {
  width: 100%;
}

@media (min-width: 768px) {
  .post {
    width: 600px;
    margin: auto;
  }
}

.post-title {
  margin: 0;
}

.post-details {
  padding: 10px;
  box-sizing: border-box;
  border-bottom: 3px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
}

@media (min-width: 768px) {
  .post-details {
    flex-direction: row;
  }
}

.post-detail {
  color: rgb(88, 88, 88);
  margin: 0 10px;
}

.post-feedback a {
  color: red;
  text-decoration: none;
}

.post-feedback a:hover,
.post-feedback a:active {
  color: salmon;
}
</style>
