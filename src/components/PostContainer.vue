<template>
    <div>
        <h1>My container</h1>
        <h2>{{ clickedChild }}</h2>
        <PostCard
            @childClicked="handleChildUpdate"
            postTitle="This is a cool post"
            :postContent="post1Content"
            :id="post1id"
        />

        <PostCard
            @childClicked="handleChildUpdate"
            postTitle="This is a cooler post"
            :postContent="post2Content"
            :id="post2id"
        />
        <PostCard
            @childClicked="handleChildUpdate"
            postTitle="This is the third post"
            postContent="Michael Jordan"
            :id="3"
        />
    </div>
</template>

<script>
import PostCard from '@/components/PostCard.vue'
    export default {
        name : "PostContainer",
        components: {
            PostCard,
        },
        data() {
            return {
                post1id: 1,
                post2id: 2,
                post1Content : "Not Lorem Ipsum",
                post2Content : "BUGS BUNNY",
                clickedChild : "Click a child"
            }
        },
        methods: {
            handleChildUpdate(postInfo) {
                this.clickedChild = postInfo;
                console.log(postInfo);
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>