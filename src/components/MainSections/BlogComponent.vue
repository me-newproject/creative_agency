<template>
    <section id="blog">
        <div class="container mt-5">
            <div class="row">

                <div class="col-lg-12">
                    <div class="title">
                        <h6>We are megaone company</h6>
                        <h2>Our
                            <span class="word" style="color: #03a9f5;" :class="{ 'capriola': cambiaParola }">
                                {{ parola }}</span>
                            will keep
                        </h2>
                        <h2>everyone updated</h2>
                    </div>
                </div>
            </div>
        </div>


        <div class="container d-flex justify-content-center align-items-center">
            <div class="row">
                <div class="col-lg-4 d-flex justify-content-center align-items-center">
                    <div class="card" style="width: 21rem;">
                        <img src="@/assets/blog-news-1.jpg" class="card-img-top" alt="img blog1">
                        <div class="card-body">
                            <h6 class="card-subtitle my-3">October 29, 2023</h6>
                            <h5 class="card-title my-2">Web design is fun</h5>
                            <p class="card-text">Lorem ipsum dolor sit amet consectetur adipiscing elit ipsum dolor sit
                                am...</p>
                        </div>
                        <div class="container d-flex  align-items-center ">
                            <img class="avatar1 my-4" src="@/assets/avatar-1.png" alt="avatar1">
                            <h5 class="author-name">Hena Sword</h5>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4 d-flex justify-content-center align-items-center">
                    <div class="card" style="width: 21rem;">
                        <img src="@/assets/blog-news-2.jpg" class="card-img-top" alt="img blog2">
                        <div class="card-body">
                            <h6 class="card-subtitle my-3">October 29, 2023</h6>
                            <h5 class="card-title my-2">Future of websites</h5>
                            <p class="card-text">Lorem ipsum dolor sit amet consectetur adipiscing elit ipsum dolor sit
                                am...</p>
                        </div>
                        <div class="container d-flex  align-items-center ">
                            <img class="avatar2 my-4" src="@/assets/avatar-2.png" alt="avatar1">
                            <h5 class="author-name">David Villas</h5>
                        </div>
                    </div>
                </div>
                <div class="col-lg-4 d-flex justify-content-center align-items-center">
                    <div class="card" style="width: 21rem;">
                        <img src="@/assets/blog-news-3.jpg" class="card-img-top" alt="img blog3">
                        <div class="card-body">
                            <h6 class="card-subtitle my-3">October 29, 2023</h6>
                            <h5 class="card-title my-2">Digital marketing</h5>
                            <p class="card-text">Lorem ipsum dolor sit amet consectetur adipiscing elit ipsum dolor sit
                                am...</p>
                        </div>
                        <div class="container d-flex  align-items-center ">
                            <img class="avatar3 my-4" src="@/assets/avatar-5.png" alt="avatar1">
                            <h5 class="author-name">John Walker</h5>
                        </div>
                    </div>
                </div>
            </div>
        </div>










    </section>

</template>


<script>
export default {
    name: "BlogComponent",
    data() {
        return {
            parola: 'latest blogs',
            parole: ['latest blogs', 'recent news'],
            indice: 0,
        };
    },
    created() {
        this.cambiaParola();
    },
    methods: {
        cambiaParola() {
            setInterval(() => {
                this.indice = (this.indice + 1) % this.parole.length;
                this.parola = this.parole[this.indice];
            }, 2000);
        },
    },
}

</script>


<style scoped>
#blog {
    background-color: #f8f9fa;
    padding: 100px;
}

.title {
    text-align: center;
    color: rgb(64, 72, 84);
    margin-bottom: 100px;
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

.card-title {
    font-size: 25px;
}

.card-text {
    font-size: 15px;
    font-weight: 300;
}

.card-subtitle {
    color: #f041b4;
    font-family: "Roboto", sans-serif;
    font-weight: 400;
}

.avatar1,
.avatar2,
.avatar3 {
    max-width: 15%;
    border-radius: 50%;
    margin-right: 15px;

}

.avatar1 {
    background-color: #03a9f5;
}

.avatar2 {
    background-color: #9556f5;
}

.avatar3 {
    background-color: #f033b5;
}

.author-name {
    font-size: 15px;
    font-weight: 500;
    color: #5d636e;
}

/*animazione*/

.card:hover {
    animation: suegiu 1s infinite;
}

@keyframes suegiu {
    0% {
        transform: translateY(0);
        /* Inizia dalla posizione originale */
    }

    50% {
        transform: translateY(-5px);
        /* Alza la card di 100px */
    }

    100% {
        transform: translateY(0);
        /* Riporta la card alla posizione originale */
    }
}



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



@media only screen and (max-width: 768px) {
#blog{
    margin: 0;
    padding: 0;
}

#blog h2,
span {
  margin: 0;
  padding: 0;
}


.title{
    margin-bottom: 30px;
   
}


.title h2{
  font-size: 30px;
  
}



.title h2, .title span {
 display: inline-block; 

}

.card{
    margin-bottom: 30px;
    width: 100%;
}



}



</style>