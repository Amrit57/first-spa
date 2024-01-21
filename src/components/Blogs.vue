<template>
    <div class="container my-4">
        <div v-for="blog in blogData" class="list-group">
            <BlogPost @deleteBlog="handleDeleteBlog" :blog="blog" />
        </div>
    </div>
</template>

<script>
import BlogPost from './BlogPost.vue'
export default ({
    props: {
        blogData: {
            type: Array,
            reruired: true
        }
    },
    components: {
        BlogPost
    },
    methods: {
        handleDeleteBlog(id) {
            this.$emit('handleDeleteBlog', id)
        }
    }
})
</script>