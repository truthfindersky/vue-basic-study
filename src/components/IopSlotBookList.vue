<template>
    <div class="container">
        <div>
            <div class="row">
                <div class="col-md-4" v-for="(book, i) in books" :key="i">
                    <IopSlotBook :book-data="book">
                        <template v-slot>
                            <button class="btn-primary">Read more</button>
                        </template>
                        <template v-slot:preview="slotProps">
                            <a :href="slotProps.previewSlug"><button class="btn-secondary ml-3">Preview</button></a>
                        </template>
                    </IopSlotBook>
                </div>
            </div>
        </div>
    </div>
</template>

<script>
import IopSlotBook from './IopSlotBook.vue'

export default {
    components: {
        IopSlotBook
    },
    data() {
        return {
            books: [
                {
                    'author': 'Cory Althoff',
                    'title': 'The Self-Taught Computer Scientist',
                    'description': 'In this book, you’ll learn more about not only being a better programmer but also about how to ace programming job interviews.',
                    'img_url': require('../assets/vue.png')
                },
                {
                    'author': 'Thomas Johnson',
                    'title': 'The Computer Science Book',
                    'description': 'This lengthy book covers countless computer science topics, from databases to operating systems. ',
                    'img_url': require('../assets/vue.png')
                },
                {
                    'author': 'T.R. Reid',
                    'title': 'The Chip',
                    'description': 'This book tells the story of Jack Kilby and Robert Noyce, and their discovery of the silicon microchip',
                    'img_url': require('../assets/vue.png')
                },
                {
                    'author': 'Erik Brynjolfsson and Andrew McAfee',
                    'title': 'The Second Machine Age',
                    'description': 'An optimistic, beautiful look at the true power behind computer science, this book is an inspiration for computer majors',
                    'img_url': require('../assets/vue.png')
                },
                {
                    'author': 'Walter Isaacson',
                    'title': 'The Innovators',
                    'description': 'In The Innovators, Walter Isaacson digs back into history to identify the driving forces behind the digital revolution',
                    'img_url': require('../assets/vue.png')
                },
                {
                    'author': 'Workman Publishing',
                    'title': 'Everything You Need to Know to Ace Computer Science and Coding',
                    'description': 'Everything You Need to Know to Ace Computer Science and Coding is the perfect book series for those who want to start learning early.',
                    'img_url': require('../assets/vue.png')
                },
            ]
        }
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

