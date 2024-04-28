<template>
    <section id="work" class="my-5 py-5">
        <div class="container mt-5">
            <div class="row">

                <div class="col-lg-12">
                    <div class="title mb-3">
                        <h6>We are megaone company</h6>
                        <h2>We have <span style="color: #03a9f5;">developed</span> some</h2>
                        <h2>great projects</h2>
                    </div>
                    <div class="title-progress">
                        <p>There are many variations of
                            passages of Lorem Ipsum available, <br>but the majority have suffered
                            alteration in some form, by injected. </p>
                    </div>

                </div>
            </div>
        </div>

        <div class="gallery-menu" id="gallery-menu">
            <a @click="filterImages('all')" :class="{ active: currentCategory === 'all' }">All</a><span>/</span>
            <a @click="filterImages('graphicdesign')" :class="{ active: currentCategory === 'graphicdesign' }">Graphic
                design</a><span>/</span>
            <a @click="filterImages('webdesign')" :class="{ active: currentCategory === 'webdesign' }">Web Design
            </a><span>/</span>
            <a @click="filterImages('seo')" :class="{ active: currentCategory === 'seo' }">SEO </a><span>/</span>
            <a @click="filterImages('marketing')" :class="{ active: currentCategory === 'marketing' }">Marketing</a>


            <div class="grid-container justify-content-center mt-5">


                <div v-for="(image, index) in images" :key="index" :class="'image-' + index" class="image-container">
                    <img class="image" :src="image.src" :alt="image.alt" :class="image.category"
                        v-show="showImage(image.category)">

                    <div class="overlay" @click="openModal(index)">
                        <div class="plus"></div>
                        <h5 class="text mb-2">Latest Work</h5>
                        <p class="text-par">See Our Amazing Work</p>
                    </div>
                </div>




                <!-- inizio modal -->
                <div v-if="showModal" class="modal" tabindex="-1" role="dialog">
                    <div class="modal-dialog modal-dialog-centered" role="document">
                        <div class="modal-content">
                            <div class="modal-header">
                            </div>
                            <div class="modal-body d-flex align-items-center">
                                <span class="w3-display-left w3-btn" @click="plusDivs(-1)"><i
                                        class="fas fa-angle-left"></i></span>
                                <img :src="images[currentIndex].src" class="mimg img-fluid" alt="Modal Image">
                                <span class="w3-display-right w3-btn" @click="plusDivs(1)"><i
                                        class="fas fa-angle-right"></i></span>
                            </div>
                        </div>
                    </div>
                    <div class="btn-x w3-text-white w3-xxlarge w3-hover-text-grey w3-container me-5" @click="closeModal"
                        style="cursor:pointer"><i class="fas fa-power-off"></i></div>
                </div>
            </div>
        </div>
    </section>
</template>


<script>
export default {
    name: "WorkComponent",

    data() {
        return {

            images: [
                { src: require('@/assets/work-1.jpg'), alt: 'Immagine 1', category: 'graphicdesign' },
                { src: require('@/assets/work-2.jpg'), alt: 'Immagine 2', category: 'seo' },
                { src: require('@/assets/work-4.jpg'), alt: 'Immagine 3', category: 'graphicdesign' },
                { src: require('@/assets/work-3.jpg'), alt: 'Immagine 4', category: 'seo' },
                { src: require('@/assets/work-5.jpg'), alt: 'Immagine 5', category: 'webdesign' },
                { src: require('@/assets/work-6.jpg'), alt: 'Immagine 6', category: 'marketing' },
                { src: require('@/assets/work-7.jpg'), alt: 'Immagine 7', category: 'webdesign' },
                { src: require('@/assets/work-8.jpg'), alt: 'Immagine 8', category: 'marketing' }
            ],
            currentCategory: 'all',
            showModal: false,
            currentIndex: 0

        };
    },
    methods: {

        filterImages(category) {
            this.currentCategory = category;
        },
        showImage(category) {
            return this.currentCategory === 'all' || category === this.currentCategory;
        },
        openModal(index) {
            this.showModal = true;
            this.currentIndex = index;
        },
        closeModal() {
            this.showModal = false;
        },
        plusDivs(n) {
            this.currentIndex += n;
            if (this.currentIndex >= this.images.length) {
                this.currentIndex = 0;
            }
            if (this.currentIndex < 0) {
                this.currentIndex = this.images.length - 1;
            }
        },
        currentDiv(n) {
            this.currentIndex = n;
        }
    },


    created() {
        this.filterImages('all');
    }
};

</script>


<style scoped>
.title,
.title-progress {
    text-align: center;
    color: rgb(64, 72, 84);
}

.title h2 {
    font-size: 40px;
    font-weight: 600;
}

.title h6 {
    font-family: "Roboto", sans-serif;
    font-size: 18px;
    font-weight: 300;
}

.title-progress {
    line-height: 2;
    font-family: "Roboto", sans-serif;
    font-size: 17px;
    font-weight: 300;
}

/*inizio sistema a grid*/


.grid-container {
    display: grid;
    grid-auto-flow: dense;
    gap: none;
    grid-template-columns: repeat(minmax(300px, 1fr));
    justify-content: center;
    align-content: center;
    grid-template-areas:
        "image-0 image-1 image-3 image-3 "
        "image-0 image-2 image-3 image-3"
        "image-4 image-4 image-5 image-5"
        "image-4 image-4 image-6 image-7";
    /* definizione delle aree di template */
}

.grid-container img {
    width: 100%;
    height: auto;
    object-fit: cover;
}


/* assegnazione delle aree di template ai singoli elementi */
.image-0 {
    grid-area: image-0;
}

.image-1 {
    grid-area: image-1;
}

.image-2 {
    grid-area: image-2;
}

.image-3 {
    grid-area: image-3;
}

.image-4 {
    grid-area: image-4;
}

.image-5 {
    grid-area: image-5;
}

.image-6 {
    grid-area: image-6;
}

.image-7 {
    grid-area: image-7;
}



/*fine sistema a grid*/

/*menu gallery*/

.gallery-menu {
    text-align: center;
    margin-bottom: 25px;
}

.gallery-menu a {
    text-decoration: none;
    color: #333;
    padding: 5px 5px;
    cursor: pointer;
    font-weight: 500;
    font-size: 15px;
    margin: 0 7px;
}

#gallery-menu a:hover {
    color: #03a9f5;

}

.active {
    color: #f041b4 !important;
    /* border-bottom: 2px solid #f041b4;  */
}


/*animazione flip in x*/

@keyframes capriola {
    0% {
        transform: perspective(400px) rotateX(90deg);

    }

    40% {
        transform: perspective(400px) rotateX(-10deg);
    }

    70% {
        transform: perspective(400px) rotateX(10deg);
    }

    100% {
        transform: perspective(400px) rotateX(0deg);

    }
}

.word {
    display: inline-block;
    animation: capriola 2s ease-out infinite;
}


/*overlay ingrandimento e testo*/
.image-container {
    position: relative;
    overflow: hidden;
}


.overlay {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    /* background: -moz-linear-gradient(left, #237bfed5 2%, #03a8f5e2 82%);
    background: -webkit-linear-gradient(left, #237bfece 2%, #03a8f5dc 82%); */
    background: linear-gradient(to right, #237bfecc 2%, #03a8f5d0 82%);
    opacity: 0;
    transition: opacity 0.5s ease;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    cursor: pointer;

}

.image-container:hover .overlay {
    opacity: 1;

}

.image-container:hover img {
    transform: scale(1.2);
    transition: transform 0.5s ease;
}

.text {
    text-align: center;
    color: white;

}

.text-par {
    text-align: center;
    color: white;
    font-family: "Roboto", sans-serif;
    font-weight: 200;
    font-size: 12px;
    transform: translateY(50%);
}

/*tasto più*/
.plus {
    display: block;
    margin: 0 auto;
    height: 70px;
    width: 70px;
    position: relative;
    overflow: hidden;
    margin-bottom: 1rem;
}


.plus::before {
    width: 2px;
    margin-left: -1px;
    left: 50%;
    top: 5px;
    bottom: 5px;
}

.plus::after {
    height: 2px;
    margin-top: -1px;
    top: 50%;
    left: 5px;
    right: 5px;
}

.plus::before,
.plus::after {
    content: " ";
    position: absolute;
    background: #fff;
}


/*inizio modal*/



.modal-header {
    border-bottom: none;
}

.modal {
    background: rgba(0, 0, 0, 0.721);
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    scrollbar-width: none;
    /* Firefox */
}

.modal::-webkit-scrollbar {
    display: none;
    /* Chrome, Safari, Opera */
}


.modal-dialog {
    max-width: 90%;

}

.modal-content {
    background-color: transparent;
    border: none;

}

.fa-angle-right,
.fa-angle-left {
    font-size: 22px;
    color: white;
    border-radius: 50%;
    border: 2px solid white;
    height: 45px;
    width: 45px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    position: fixed;
}


.modal-body img {
    object-fit: none;
}

.modal-body {
    min-width: 92vw;
    min-height: 30vh;
    overflow: hidden;
    display: flex;
    align-items: center;
    position: relative;
}




/*modal btn*/

.btn-x {
    top: 0;
    transform: translateY(-250px);
    font-size: 25px;
    border: 2px solid white;
    color: white;
    display: flex;
    justify-content: center;
    align-items: center;
    background: transparent;
    border-radius: 50%;
    width: 46px;
    height: 46px;
    z-index: 100;
    text-align: center;
    line-height: 46px;
}

@media only screen and (max-width: 768px) {

    #work {
        margin: 0;
        padding: 0;
    }


    .gallery-menu a{

        margin-right: 20px;
          
    }

    .title,
    h2,
    .par {

        text-align: center;
    }


    .title-progress br {
        display: none;
    }

    .title h2 {
        font-size: 30px;
    }

    .grid-container {
        display: flex;
        flex-direction: column;
        margin: 20px 20px;
        gap: 20px;
    }

    .btn-x {
        border: none;
        transform: translateY(-200px);

    }


    .modal-body img {
        object-fit: cover;

    }


    .modal-dialog {
        max-width: 70%;
    }


    .fa-angle-right,
    .fa-angle-left {
        transform: translateX(-22px);
    }



}
</style>