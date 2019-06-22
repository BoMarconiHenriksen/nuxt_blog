# Pages - Routing and View
This folder is about pages, routing and views in Nuxt.js  
### Routes
Routes is created in the page folder.  
You can create a folder called users and place a index.vue file in the folder and you have a route localhost:3000/users  
### Creating a route with a dynamic path
Start the file with _ to mark that it's dynamic url like _id.vue  
```localhost:3000/users/1```  
You can also create a folder called _id and then create an index.vue file.  
https://github.com/BoMarconiHenriksen/nuxt_blog/tree/master/01_Pages_Routing_Views/routing/pages/users  
### Adding Links and Navigate Around
To create a navigation link:  
```<nuxt-link to="/users">Users</nuxt-link>```   
To interact with dynamic link:  
```
<template>
<div>
    <input type="text" v-model="userId">
    <button @click="onLoadUser">Load User</button>
</div>
    
</template>

<script>
export default {
    data() {
        return {
            userId: ''
        }
    },
    methods: {
        onLoadUser() {
            this.$router.push('/users/' + this.userId)
        }
    }
}
</script>
```
### Validating Parameters
Pages is loaded as root pages for a given url and components is used as normal building blocks.  
Nuxt offer route validation.  
```
<script>
export default {
    validate(data) {
        // Returns true if it's a number
        return /^\d+$/.test(data.params.id)
    }
}
</script>
```
### Creating Nested Routes
In the folder where the users folder is create a file called users.vue  
Use ```<nuxt-child />```  
https://github.com/BoMarconiHenriksen/nuxt_blog/tree/master/01_Pages_Routing_Views/routing/pages/users  

