<template>
    <div class="container my-2">
        <a href="#" class="list-group-item list-group-item-action active" aria-current="true">
            <div class="d-flex w-100 justify-content-between">
                <h5 class="mb-1">{{ blog.title }}</h5>
                <div>
                    <small>{{ blog.publicationDate }}</small>
                    <button @click="deleteBlog(blog.id)" class="btn btn-danger ms-2 btn-sm"> X</button>

                </div>
            </div>
            <p class="mb-1">{{ blog.content }}</p>
            <small>{{ blog.author }}</small>
        </a>
    </div>
</template>

<script>
export default ({
    props: {
        blog: {
            type: Object,
            required: true
        }
    },
    methods: {
        deleteBlog(id) {
            this.$emit('deleteBlog', id)
        }
    }
})
</script>