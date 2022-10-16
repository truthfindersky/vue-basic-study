<template>
    <div>
        <div class="card">
            <img :src="bookData.img_url" class="card-img-top">
            <div class="card-body">
                <p class="card-text">Title: {{bookData.title}}</p>
                <p class="card-text">Author: {{bookData.author}}</p>
                <p class="card-text">Description: {{bookData.description}}</p>
                <slot></slot>
                <slot name="preview" :previewSlug="previewSlug"></slot>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        bookData: {
            type: Object,
            required: true,
            default: () => { }
        }
    },
    methods: {
        computePreviewSlug() {
            return this.bookData.title.split(' ').join('-') + '-' + this.bookData.author.split(' ').join('-')
        },
    },
    computed: {
        previewSlug() {
            return this.computePreviewSlug()
        },
    }
}
</script>








































<!-- <template>

        <div class="col-sm-12 col-md-4 col-lg-3">
        <div class="card" style="width: 18rem;">
            <img class="card-img-top" src="../assets/download.svg" alt="Card image cap">
            <div class="card-body">
                <h5 class="card-title">{{contentName}}</h5>
                <p class="card-text">{{contentTitle}}</p>
                <a href="#" class="btn btn-primary">Go somewhere</a>
            </div>
        </div>
        </div>
        
    <br>
</template>

<script>
export default {
    name: 'IopSlot',
    props: ['contentName', 'contentTitle']
}
</script> -->

