<template>
    <div>
        <h1>My smart container {{ userInput }}</h1>
        <h2>{{ clickedChild }}</h2>
        <input v-model="userInput" type="text">
        <input v-model="isChecked" type="checkbox"> {{isChecked}}
        <PostCard v-for="post in posts"
            :key="post.id"
            :postTitle="post.postTitle"
            :postContent="post.postContent"
            :id="post.id"
        />
   <!-- Without explicitly binding each field, 1:1 mapping to props -->
        <!-- <PostCard v-for="post in posts"
            :key="post.id"
            v-bind="post"
        /> -->

    </div>
</template>

<script>
import PostCard from './PostCard.vue'
    export default {
        components: { PostCard },
        name : "SmartContainer",
        data() {
            return {
                userInput : "Hello",
                isChecked : false,
                posts: [
                    {
                        id : 1,
                        postTitle : "Cheese Pizza",
                        postContent : "Put cheese on dough",
                        author : "Jack"
                    },
                    {
                        id : 2,
                        postTitle : "Hawaiian Pizza",
                        postContent : "Pineapples belong on pizza (?)"
                    },
                    {
                        id : 3,
                        postTitle : "Veggie Pizza",
                        postContent : "Mushrooms, peppers, onions, tomatoes"
                    },
                    {
                        id : 4,
                        postTitle : "Pepperoni Pizza",
                        postContent : "Classic choice"
                    },
                    {
                        id : 5,
                        postTitle : "BBQ CHICKEN",
                        postContent : "If you are REALLY excited about chicken"
                    },
                    {
                        id : 6,
                        postTitle : "Hawaiian Pizza",
                        postContent : "Pineapples belong on pizza (?)"
                    },
                    
                ]
            }
        },

        methods: {
        
        },
    }
</script>

<style lang="scss" scoped>

</style>