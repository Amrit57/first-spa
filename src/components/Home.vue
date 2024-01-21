<template>
    <Navbar />
    <Blogs @handleDeleteBlog="handleDeleteBlog" :blogData="blogData" />
</template>
<script>
import Navbar from './Navbar.vue';
import Blogs from './Blogs.vue'
export default ({
    components: {
        Navbar, Blogs
    },
    data() {
        return {
            url: 'http://localhost:3000/blogPosts',
            blogData: []
        }
    },
    created() {
        this.fetchData()
    },
    methods: {
        async fetchData() {
            const res = await fetch(this.url);
            const data = await res.json()
            return this.blogData = data;

        },
        handleDeleteBlog(id) {
            this.blogData = this.blogData.filter(blog => blog.id !== id)

        }
    }
})
</script>