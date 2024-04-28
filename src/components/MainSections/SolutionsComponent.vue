<template>
    <section id="solutions" class="my-5 py-5">
        <div class="container mt-5">
            <div class="row">

                <div class="col-lg-6">
                    <div class="title mb-3">
                        <h6>We are megaone company</h6>
                        <h2><span class="word" style="color: #f041b4;" :class="{ 'capriola': cambiaParola }">
                                {{ parola }}</span> and</h2>
                        <h2>Development Solutions</h2>
                    </div>
                    <div class="title-progress">
                        <p class="par">There are many variations of passages of Lorem Ipsum available,
                            but the majority have suffered alteration in some form, by injected
                            humour, or randomised words which don't look even slightly believable.
                            If you are going to use a passage of Lorem Ipsum. </p>
                    </div>

                    <div class="ball ">
                        <ul>
                            <li>
                                <a>
                                    Learn More
                                    <span></span><span></span><span></span><span></span>
                                </a>
                            </li>
                        </ul>
                    </div>

                </div>

                <div class="col-lg-6">
                    <img src="@/assets/table-art-4.png" alt="desk" class="img-fluid desk">

                </div>
            </div>
        </div>
    </section>

</template>


<script>
export default {
    name: "SolutionsComponent",
    data() {
        return {
            parola: 'Robust Designed',
            parole: ['Robust Designed', 'Creative Idea'],
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
#solutions {
    background-color: #f8f9fa;
}

#solutions img {
    width: 100%;

}

.title,
.title-progress {
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



/*inizio button


/*button bubble*/

.ball ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    cursor: pointer;
}

.ball ul li {
    background-color: #03a9f5;
    --c: #f021b6;
    color: white;
    font-size: 14px;
    border-radius: 50px;
    text-align: center;
    position: relative;
    overflow: hidden;
    z-index: 2;
    transition: 0.5s;
    padding: 14px 20px;
    font-weight: 500;
    width: 160px;
    height: auto;
    border: 1px solid transparent;

}

.ball ul li span {
    position: absolute;
    width: 25%;
    height: 100%;
    background-color: var(--c);
    transform: translateY(150%);
    border-radius: 50%;
    left: calc((var(--n) - 1) * 25%);
    transition: 0.5s;
    transition-delay: calc((var(--n) - 1) * 0.1s);
    z-index: -1;

}

.ball ul li:hover {
    background-color: white;
    color: white;
    border: 1px solid #f021b6;
}

.ball ul li:hover span {
    transform: translateY(0) scale(2);
}

.ball ul li span:nth-child(1) {
    --n: 1;
}

.ball ul li span:nth-child(2) {
    --n: 2;
}

.ball ul li span:nth-child(3) {
    --n: 3;
}

.ball ul li span:nth-child(4) {
    --n: 4;
}

/*fine button bubble*/

@media only screen and (max-width: 768px) {



    .title h2 {
        font-size: 30px;

    }


    .ball {
        margin-bottom: 20px;
        display: flex;
        justify-content: center;
        align-items: center;

    }

    .title,
    h2,
    .par {

        text-align: center;
    }



}


</style>