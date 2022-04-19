<template>
    <div @click="notifyParent">
        <img v-if="starred" src="https://as1.ftcdn.net/v2/jpg/01/09/84/42/1000_F_109844239_A7MdQSDf4y1H80cfvHZuSa0zKBkZ68S7.jpg" alt="">
        <h3>{{ postTitle }}</h3>
        <p>{{ postContent }}</p>
    </div>
</template>

<script>
    export default {
        name : "PostCard",
        props: {
            postTitle: String,
            postContent : String,
            id : Number,
            
        },
        data() {
            return {
                starred: false
            }
        },
        methods: {
            notifyParent() {
                this.$emit('childClicked', this.postContent);
                this.$root.$emit('childStar', this.id);
            },
            updatedStar(postId){
                if (this.id == postId){
                    this.starred = true;
                }else{
                    this.starred = false;
                }
            }
        },

        mounted () {
            this.$root.$on('childStar', this.updatedStar);
        },
    }
</script>

<style lang="scss" scoped>
div {
    border : solid 2px white;
    background-color: rgb(75, 75, 75);
    h3 {
        color : navy;
        display: inline;
    }
    p {
        color : rgb(25, 232, 232);
        font-style : italic;
    }
    img{
        height: 1.5em;
    }
}

</style>