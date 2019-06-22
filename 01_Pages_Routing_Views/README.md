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
### Layout, Pages and Components
Layout is the template. All pages is wrapped with the layout.  
Pages can have nested pages and use components.  
Components is small reuseable blocks.  
### Adding a new Layout
In the layouts folder change the default.vue file to change the style.  
In the layout folder create a file called users.vue and style it.  
In the pages folder find the users.vue file and in the script tag add.  
```layout: 'users'``` to use the layout.  
If there is a nested route you need to add there also.  
### Adding a Default Error Page
In the layouts folder add an ```error.vue``` file.  
It's a reserved name and will be load everytime the app througs an error like 404.  
### Working with Components
Components render as part of a page.  
Create a header component in the components folder.  


