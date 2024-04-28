<template>
    <section id="about" class="my-5">
        <div class="container">
            <div class="row">

                <div class="col-lg-6">
                    <div class="title mb-3">
                        <h6>We are megaone company</h6>
                        <h2>We are making <span class="word" style="color: #03a9f5;"
                                :class="{ 'capriola': cambiaParola }">
                                {{ parola }}</span></h2>
                        <h2>better for everyone</h2>
                    </div>
                    <p class="par">There are many variations of passages of Lorem Ipsum available,
                        but the majority have suffered alteration in some form, by injected humour,
                        or randomised words which don't look even slightly believable. If you are going
                        to use a passage of Lorem Ipsum. </p>
                    <div>

                        <div>
                            <div class="ball ">
                                <ul>
                                    <li>
                                        <a>Learn More
                                            <span></span><span></span><span></span><span></span>
                                        </a>
                                    </li>
                                </ul>
                            </div>
                        </div>



                    </div>

                </div>

                <div class="col-lg-6">
                    <img src="@/assets/desk-art-2.png" alt="desk" class="img-fluid desk">

                </div>
            </div>
        </div>




    </section>



    <section id="services">
        <div class="container py-5">
            <div class="row">
                <div class="col-md-3">
                    <div class="tico-serie">
                        <span class="ico-service blue"><i aria-hidden="true" class="fas fa-folder-open"></i></span>
                        <h4 class="service-testo">World leader in consulting <br> and finance</h4>
                    </div>
                </div>
                <div class="col-md-3">
                    <div class="tico-serie">
                        <span class="ico-service midnight"><i aria-hidden="true" class="fas fa-code"></i></span>
                        <h4 class="service-testo">A focused team with a <br> specialized skill</h4>
                    </div>
                </div>
                <div class="col-md-3">
                    <div class="tico-serie">
                        <span class="ico-service purple"><i aria-hidden="true" class="fas fa-cog"></i></span>
                        <h4 class="service-testo">Trusted and professional <br> advisors for you</h4>
                    </div>
                </div>
                <div class="col-md-3">
                    <div class="tico-serie">
                        <span class="ico-service pink"><i aria-hidden="true" class="fas fa-edit"></i></span>
                        <h4 class="service-testo">Experience to give you a <br> better results</h4>
                    </div>
                </div>
            </div>
        </div>
    </section>

</template>


<script>

export default {
    name: "AboutComponent",
    data() {
        return {
            parola: 'ideas',
            parole: ['ideas', 'design'],
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
    beforeUnmount() {
        clearInterval(this.intervallo);
    },
}

</script>


<style scoped>
#about {
    font-family: "Roboto", sans-serif;
    padding-top: 100px;
}


#about img {
    max-width: 100%;

}



.par,
#about h6 {
    line-height: 30px;
    letter-spacing: 1px;
    font-weight: 300;
    font-size: 16px;
    margin-bottom: 30px;
    color: #404854;
}

#about h6 {
    font-weight: 400;
}

#about h2 {
    font-size: 40px;
    font-family: "Montserrat", sans-serif;
    font-weight: 600;
    color: #404854;

}



/*sezione services*/




/*inizio animazione flip in x*/



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

/*fine animazione*/



/*button bubble*/

.ball ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    cursor: pointer;
}

.ball ul li {
    background-color: #f021b6;
    --c: #03a9f5;
    color: white;
    font-size: 14px;
    border-radius: 50px;
    text-align: center;
    position: relative;
    overflow: hidden;
    z-index: 2;
    transition: 0.5s;
    padding: 14px 20px;
    font-weight: 400;
    width: 160px;
    height: auto;
    letter-spacing: 0.1em;
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

/*--n è una variabile CSS utilizzata per controllare 
la posizione orizzontale degli elementi span all'interno degli elementi
 li, permettendo di creare un effetto visivo dinamico quando l'elemento 
 li viene passato sopra con il mouse.*/

.ball ul li:hover {
    background-color: white;
    color: white;
    border: 1px solid #03a9f5;
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


/*inizio button con box-shadow*/

.tico-serie {
    text-align: center;
    cursor: pointer;
}

.tico-serie>.service-testo {
    font-size: 17px;
    line-height: 1.5;
    font-weight: 500;
    margin-top: 20px;
}

.tico-serie>.ico-service {
    position: relative;
    z-index: 1;
}

.tico-serie>.ico-service {
    display: inline-block;
    height: 90px;
    width: 90px;
    line-height: 90px;
    font-size: 28px;
    font-weight: 600;
    color: #fff;
    text-align: center;
    -webkit-border-radius: 50%;
    border-radius: 50%;
    -webkit-transition: all .3s ease;
    -o-transition: all .3s ease;
    transition: all .3s ease;
}

.tico-serie:hover>.ico-service::before {
    content: "";
    background: transparent;
    top: 1px;
    left: 1px;
    bottom: 1px;
    right: 1px;
    position: absolute;
    -webkit-border-radius: 50%;
    border-radius: 50%;
    border: 4px solid #fff;
    -webkit-transition: all .3s ease-in-out;
    -moz-transition: all .3s ease-in-out;
    -ms-transition: all .3s ease-in-out;
    -o-transition: all .3s ease-in-out;
    transition: all .3s ease-in-out;
}

/*blue*/

.tico-serie>.ico-service.blue {
    background: #03a9f5;
}

.tico-serie:hover .ico-service.blue {
    -webkit-animation: itg_pulse_blue 1s infinite;
    -o-animation: itg_pulse_blue 1s infinite;
    animation: itg_pulse_blue 1s infinite;
    -webkit-box-shadow: 0 0 0 0 rgb(0, 188, 212);
    box-shadow: 0 0 0 0 rgb(0, 188, 212);
}

/*inizio animazione blue*/
@-webkit-keyframes itg_pulse_blue {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(0, 188, 212, 0.9);
        box-shadow: 0 0 0 5px rgba(0, 188, 212, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(0, 188, 212, 0.6);
        box-shadow: 0 0 0 10px rgba(0, 188, 212, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(0, 188, 212, 0.3);
        box-shadow: 0 0 0 15px rgba(0, 188, 212, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(100, 48, 148, 0.1);
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

@-o-keyframes itg_pulse_blue {
    0% {
        box-shadow: 0 0 0 5px rgba(0, 188, 212, 0.9);
    }

    25% {
        box-shadow: 0 0 0 10px rgba(0, 188, 212, 0.6);
    }

    70% {
        box-shadow: 0 0 0 15px rgba(0, 188, 212, 0.3);
    }

    100% {
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

@keyframes itg_pulse_blue {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(0, 188, 212, 0.9);
        box-shadow: 0 0 0 5px rgba(0, 188, 212, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(0, 188, 212, 0.6);
        box-shadow: 0 0 0 10px rgba(0, 188, 212, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(0, 188, 212, 0.3);
        box-shadow: 0 0 0 15px rgba(0, 188, 212, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(100, 48, 148, 0.1);
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

/*midnight*/

.tico-serie>.ico-service.midnight {
    background: #41526b;
}

.tico-serie:hover .ico-service.midnight {
    -webkit-animation: itg_pulse_midnight 1s infinite;
    -o-animation: itg_pulse_midnight 1s infinite;
    animation: itg_pulse_midnight 1s infinite;
    -webkit-box-shadow: 0 0 0 0 rgb(65, 82, 107);
    box-shadow: 0 0 0 0 rgb(65, 82, 107);
}

/*animazione midnight*/

@-webkit-keyframes itg_pulse_midnight {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(65, 82, 107, 0.9);
        box-shadow: 0 0 0 5px rgba(65, 82, 107, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(65, 82, 107, 0.6);
        box-shadow: 0 0 0 10px rgba(65, 82, 107, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(65, 82, 107, 0.3);
        box-shadow: 0 0 0 15px rgba(65, 82, 107, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(100, 48, 148, 0.1);
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

@-o-keyframes itg_pulse_midnight {
    0% {
        box-shadow: 0 0 0 5px rgba(65, 82, 107, 0.9);
    }

    25% {
        box-shadow: 0 0 0 10px rgba(65, 82, 107, 0.6);
    }

    70% {
        box-shadow: 0 0 0 15px rgba(65, 82, 107, 0.3);
    }

    100% {
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

@keyframes itg_pulse_midnight {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(65, 82, 107, 0.9);
        box-shadow: 0 0 0 5px rgba(65, 82, 107, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(65, 82, 107, 0.6);
        box-shadow: 0 0 0 10px rgba(65, 82, 107, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(65, 82, 107, 0.3);
        box-shadow: 0 0 0 15px rgba(65, 82, 107, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(100, 48, 148, 0.1);
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

/*purple*/

.tico-serie>.ico-service.purple {
    background: #9556f5;
}

.tico-serie:hover .ico-service.purple {
    -webkit-animation: itg_pulse_purple 1s infinite;
    -o-animation: itg_pulse_purple 1s infinite;
    animation: itg_pulse_purple 1s infinite;
    -webkit-box-shadow: 0 0 0 0 rgb(149, 86, 245);
    box-shadow: 0 0 0 0 rgb(149, 86, 245);
}

/*animazione purple*/
@-webkit-keyframes itg_pulse_purple {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(149, 86, 245, 0.9);
        box-shadow: 0 0 0 5px rgba(149, 86, 245, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(149, 86, 245, 0.6);
        box-shadow: 0 0 0 10px rgba(149, 86, 245, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(149, 86, 245, 0.3);
        box-shadow: 0 0 0 15px rgba(149, 86, 245, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(149, 86, 245, 0.1);
        box-shadow: 0 0 0 20px rgba(149, 86, 245, 0.1);
    }
}

@-o-keyframes itg_pulse_purple {
    0% {
        box-shadow: 0 0 0 5px rgba(149, 86, 245, 0.9);
    }

    25% {
        box-shadow: 0 0 0 10px rgba(149, 86, 245, 0.6);
    }

    70% {
        box-shadow: 0 0 0 15px rgba(149, 86, 245, 0.3);
    }

    100% {
        box-shadow: 0 0 0 20px rgba(100, 48, 148, 0.1);
    }
}

@keyframes itg_pulse_purple {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(149, 86, 245, 0.9);
        box-shadow: 0 0 0 5px rgba(149, 86, 245, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(149, 86, 245, 0.6);
        box-shadow: 0 0 0 10px rgba(149, 86, 245, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(149, 86, 245, 0.3);
        box-shadow: 0 0 0 15px rgba(149, 86, 245, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(149, 86, 245, 0.1);
        box-shadow: 0 0 0 20px rgba(149, 86, 245, 0.1);
    }
}


/*pink*/

.tico-serie>.ico-service.pink {
    background: #f021b6;
}

.tico-serie:hover .ico-service.pink {
    -webkit-animation: itg_pulse_pink 1s infinite;
    -o-animation: itg_pulse_pink 1s infinite;
    animation: itg_pulse_pink 1s infinite;
    -webkit-box-shadow: 0 0 0 0 rgb(240, 33, 182);
    box-shadow: 0 0 0 0 rgb(240, 33, 182);
}


/*animazione pink*/

@-webkit-keyframes itg_pulse_pink {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(240, 33, 182, 0.9);
        box-shadow: 0 0 0 5px rgba(240, 33, 182, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(240, 33, 182, 0.6);
        box-shadow: 0 0 0 10px rgba(240, 33, 182, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(240, 33, 182, 0.3);
        box-shadow: 0 0 0 15px rgba(240, 33, 182, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(240, 33, 182, 0.1);
        box-shadow: 0 0 0 20px rgba(240, 33, 182, 0.1);
    }
}

@-o-keyframes itg_pulse_pink {
    0% {
        box-shadow: 0 0 0 5px rgba(240, 33, 182, 0.9);
    }

    25% {
        box-shadow: 0 0 0 10px rgba(240, 33, 182, 0.6);
    }

    70% {
        box-shadow: 0 0 0 15px rgba(240, 33, 182, 0.3);
    }

    100% {
        box-shadow: 0 0 0 20px rgba(240, 33, 182, 0.1);
    }
}

@keyframes itg_pulse_pink {
    0% {
        -webkit-box-shadow: 0 0 0 5px rgba(240, 33, 182, 0.9);
        box-shadow: 0 0 0 5px rgba(240, 33, 182, 0.9);
    }

    25% {
        -webkit-box-shadow: 0 0 0 10px rgba(240, 33, 182, 0.6);
        box-shadow: 0 0 0 10px rgba(240, 33, 182, 0.6);
    }

    70% {
        -webkit-box-shadow: 0 0 0 15px rgba(240, 33, 182, 0.3);
        box-shadow: 0 0 0 15px rgba(240, 33, 182, 0.3);
    }

    100% {
        -webkit-box-shadow: 0 0 0 60px rgba(240, 33, 182, 0.1);
        box-shadow: 0 0 0 20px rgba(240, 33, 182, 0.1);
    }
}


@media only screen and (max-width: 768px) {



#about h2,
span {
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

.service-testo{
    text-align: center;
    margin-bottom: 10px;
   
}



.service-testo br{
    display: none;
}


}

</style>
