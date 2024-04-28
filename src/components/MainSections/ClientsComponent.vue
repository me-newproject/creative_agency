<template>
    <section id="clients">
        <div class="container">
            <i class="fas fa-quote-left"></i>
            <div class="row">
                <div class="col-lg-12">

                    <div class="title">
                        <h2>Some <span class="word" :class="{ 'capriola': cambiaParola }">
                                {{ parola }}</span> words from </h2>
                        <h2 class="our" >our clients</h2>
                    </div>
                </div>
            </div>
            <div class="row ">
                <div class="col-lg-2">
                    <div class="avatar d-flex">
                        <img class="homo-1" src="@/assets/avatar-1.png" alt="">
                        <img class="homo-2" src="@/assets/avatar-2.png" alt="">


                    </div>
                    <div class="avatar d-flex">
                        <img class="homo-3" src="@/assets/avatar-3.png" alt="">
                        <img class="homo-7" src="@/assets/avatar-7.png" alt="">
                    </div>
                </div>
                <div class="col-lg-8">

                    <div id="carouselExampleAutoplaying" class="carousel slide" data-bs-ride="carousel">
                        <div class="carousel-inner">
                            <div class="carousel-item active">

                                <p class="par mx-3">

                                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse tincidunt
                                    egestas nunc, at pellentesque arcu sollicitudin et. Aliquam hendrerit diam quis
                                    ipsum
                                    ultricies, quis ultricies arcu suscipit. Lorem ipsum dolor sit amet,
                                    consectetur adipiscing
                                    elit. Fusce ut diam quis nulla faucibus venenatis.
                                </p>
                                <h5 class="author">David Villas</h5>
                                <p class="job">Designer, Company Name</p>
                                <ul class="star d-flex justify-content-center">
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                </ul>
                            </div>
                            <div class="carousel-item">
                                <p class="par mx-3">
                                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse tincidunt
                                    egestas nunc, at pellentesque arcu sollicitudin et. Aliquam hendrerit diam quis
                                    ipsum
                                    ultricies, quis ultricies arcu suscipit. Lorem ipsum dolor sit amet,
                                    consectetur adipiscing
                                    elit. Fusce ut diam quis nulla faucibus venenatis.
                                </p>
                                <h5 class="author">David Villas</h5>
                                <p class="job">Designer, Company Name</p>
                                <ul class="star d-flex justify-content-center">
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                </ul>
                            </div>
                            <div class="carousel-item">
                                <p class="par mx-3">
                                    Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse tincidunt
                                    egestas nunc, at pellentesque arcu sollicitudin et. Aliquam hendrerit diam quis
                                    ipsum
                                    ultricies, quis ultricies arcu suscipit. Lorem ipsum dolor sit amet,
                                    consectetur adipiscing
                                    elit. Fusce ut  diam quis nulla faucibus venenatis.
                                </p>
                                <h5 class="author">David Villas</h5>
                                <p class="job">Designer, Company Name</p>
                                <ul class="star d-flex  justify-content-center">
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                    <li><i class="fas fa-star px-1"></i></li>
                                </ul>
                            </div>
                        </div>
                        <!--<button class="carousel-control-prev" type="button" data-bs-target="#carouselExampleAutoplaying"
                            data-bs-slide="prev">
                            <span class="carousel-control-prev-icon" aria-hidden="true"></span>
                            <span class="visually-hidden">Previous</span>
                        </button>
                        <button class="carousel-control-next" type="button" data-bs-target="#carouselExampleAutoplaying"
                            data-bs-slide="next">
                            <span class="carousel-control-next-icon" aria-hidden="true"></span>
                            <span class="visually-hidden">Next</span>
                        </button>-->



                    </div>
                </div>
                <div class="col-lg-2">
                    <div class="avatar d-flex">
                        <img class="homo-1" src="@/assets/avatar-5.png" alt="">
                        <img class="homo-2" src="@/assets/avatar-6.png" alt="">

                    </div>
                    <div class="avatar d-flex">
                        <img class="homo-4" src="@/assets/avatar-4.png" alt="">
                        <img class="homo-5" src="@/assets/avatar-2.png" alt="">
                    </div>
                </div>



            </div>
        </div>




    </section>

</template>


<script>
export default {
    name: "ClientsComponent",
    data() {
        return {
            parola: 'ideal',
            parole: ['ideal', 'great'],
            indice: 0,
            isAnimating: false,
        };
    },
    created() {
        this.cambiaParola();
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
    },
    beforeUnmount() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        cambiaParola() {
            setInterval(() => {
                this.indice = (this.indice + 1) % this.parole.length;
                this.parola = this.parole[this.indice];
            }, 2000);

        },
        handleScroll() {
            if (!this.isAnimating) {
                if (window.scrollY > 5000) {
                    this.isAnimating = true;
                    this.applySequentialAnimation();
                }
            }
        },
        applySequentialAnimation() {
            const avatars = document.querySelectorAll('.avatar img');
            avatars.forEach((avatar, index) => {
                const delay = index * 3; // ritardo progressivo di 3 secondi per elemento
                avatar.classList.add('sequential-animation');
                avatar.style.animationDelay = `${delay}s`;
                avatar.addEventListener('animationend', () => {
                    avatar.classList.remove('sequential-animation');

                });
            });


        },
    }
}

</script>


<style scoped>
.container {
    position: relative;
}

#clients {
    background: linear-gradient(to right, #3264f5 2%, #7004bc 82%);
    height: 680px;
    padding: 100px;

}

.title h2 {
    text-align: center;
    color: white;
    font-size: 40px;
    font-weight: 600;
}


.par {
    text-align: center;
    color: white;
    font-family: "Roboto", sans-serif;
    font-size: 18px;
    font-weight: 300;
    font-style: italic;
    padding: 30px;
    line-height: 35px;

}

.virgole {
    color: #6b3bd4f9;
    font-size: 40px;
    position: absolute;
    justify-content: center;
}



.author {

    text-align: center;
    font-size: 22px;
    background: #f033b5;
    background: -moz-linear-gradient(left, #f033b5 2%, #f2a2af 82%);
    background: -webkit-linear-gradient(left, #f033b5 2%, #f2a2af 82%);
    background: linear-gradient(to right, #f033b5 2%, #f2a2af 82%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#f033b5', endColorstr='#f2a2af', GradientType=1);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
}

.job {
    color: white;
    text-align: center;
    font-family: "Roboto", sans-serif;
    font-weight: 300;
    font-size: 17px;
}

.fa-star {
    color: #ffce22;
    font-size: 14px;
    text-align: center;

}

ul {
    list-style-type: none;
    padding-left: 0;
}

.avatar img {
    background-color: white;
    border-radius: 50%;
    max-width: 71px;
    display: inline-block;
    /*border: 5px solid white;*/
    border: 5px solid rgba(255, 255, 255, .3);
    -webkit-animation: pulse_effect 1s 3;
    /*3 ripetizioni*/
    -o-animation: pulse_effect 1s 3;
    animation: pulse_effect 1s 3;
    -webkit-box-shadow: 0 0 0 0 rgb(255, 255, 255);
    box-shadow: 0 0 0 0 rgb(255, 255, 255);

}

.avatar img.sequential-animation {
    animation-delay: 10s;

}


@keyframes pulse_effect {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(255, 255, 255, 0.9);
        box-shadow: 0 0 0 5px rgba(255, 255, 255, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(255, 255, 255, 0.6);
        box-shadow: 0 0 0 10px rgba(255, 255, 255, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(255, 255, 255, 0.3);
        box-shadow: 0 0 0 15px rgba(255, 255, 255, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(255, 255, 255, 0.1);
        box-shadow: 0 0 0 20px rgba(255, 255, 255, 0.1);
    }
}



.homo-1 {
    transform: translateY(-100px);


}

.homo-2 {

    transform: translateX(60px);


}

.homo-3 {
    transform: translateY(80px);
}

.homo-7 {
    transform: translateY(200px);
    margin-left: 120px;
}

.homo-5 {

    transform: translateY(190px);
    margin-left: -120px;


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

#testimonials-avatar .owl-dot {
    position: absolute;
    border-radius: 50%;
    margin: 0;
    z-index: 1;
    padding: 0;
    opacity: 1;
    background-color: #fff;
    height: 80px;
    width: 80px;
    overflow: hidden;
    display: inline-block;
    border: 5px solid rgba(255, 255, 255, .3);
}

#testimonials-avatar .owl-dot.active {
    -webkit-animation: pulse_effect 1s infinite;
    -o-animation: pulse_effect 1s infinite;
    animation: pulse_effect 1s infinite;
    -webkit-box-shadow: 0 0 0 0 rgb(255, 255, 255);
    box-shadow: 0 0 0 0 rgb(255, 255, 255);
}

.fa-quote-left {
    color: rgba(255, 255, 255, 0.105);
    font-size: 200px;
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    z-index: 0;
}

@media only screen and (max-width: 768px) {

#clients{
    height: auto;
}

#clients,
h2,
span {
  margin: 0;
  padding: 0;
}

.title,
h2,
.par {
    padding: 0;
    text-align: center;
}

.par{
    margin-top: 15px;
}


.title h2{
  font-size: 30px;
  margin-top: 40px;
}

#clients .our{
    margin: 0;
    padding: 0;
  
}

.title h2, .title span {
 display: inline-block; 

}


.avatar img {
    display: none;
}

.fa-star{
    margin-bottom: 20px;
}




}


</style>