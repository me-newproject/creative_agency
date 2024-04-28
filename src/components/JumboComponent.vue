<template>
    <section id="jumbo">
        <div class="mouse-follower" :style="{ left: x + 'px', top: y + 'px' }"></div>
        <div class="container">
            <div class="row ">
                <div class="col-lg-6 d-flex  justify-content-end pe-4">
                    <img src="@/assets/vector-art-1.png" alt="" class="vector img-fluid animated">
                </div>
                <div class="col-lg-6 d-flex flex-column justify-content-center">
                    <h1 class="fuksia">Creative</h1>
                    <span class="digital">Digital Agency</span>
                    <div>
                        <p class="dolor py-3">Lorem ipsum dolor sit amet consectetur
                            adipisicing elit. <br>
                            Iure unde suscipit, dolorem dolores voluptatum, <br>
                            architecto magni possimus
                            maiores necessitatibus obcaecati
                        </p>
                    </div>


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

        <div>
            <a class="scroll-down" @click="scrollToAbout">Scroll Down <i class="fas fa-arrow-down mx-3"></i></a>

        </div>
        <img class="cerchio" src="@/assets/shape-7.png" alt="">
        <img class="rettangolo" src="@/assets/shape-8.png" alt="">


    </section>



</template>


<script>
export default {
    name: "JumboComponent",

    data() {
        return {
            x: 0,
            y: 0
        };
    },
    mounted() {
        window.addEventListener('mousemove', this.updatePosition);
    },
    beforeUnmount() {
        window.removeEventListener('mousemove', this.updatePosition);
    },
    methods: {
        updatePosition(e) {
            this.x = e.clientX;
            this.y = e.clientY;
        },
        scrollToAbout() {
            const aboutSection = document.getElementById('about');
            if (aboutSection) {
                aboutSection.scrollIntoView({ behavior: 'smooth' });
            }
        }

    }
}

</script>


<style scoped>
.mouse-follower {
    position: absolute;
    width: 30px;
    height: 30px;
    border-radius: 50%;
    border: 2px solid white;
    background-color: none;
    pointer-events: none;
    /* Questo permette al mouse di passare attraverso il cerchio */

}


#jumbo {
    background: linear-gradient(to right, #3264f5 2%, #7004bc 82%);
    padding: 100px;
    overflow: hidden;
    position: relative;
    height: 100vh;
    width: 100vw;
}


#jumbo img {
    max-width: 100%;

}

.vector {
    width: 50%;
}


.animated {
    animation: move-right-left 2s ease-in-out infinite alternate-reverse;
}

@keyframes move-right-left {
    0% {
        transform: translateX(20px);
    }

    100% {
        transform: translateX(-20px);
    }
}


.fuksia {
    font-weight: 800;
    font-size: 45px;
    margin-bottom: 0;
    background: #f033b5;
    background: -moz-linear-gradient(left, #f033b5 2%, #f2a2af 82%);
    background: -webkit-linear-gradient(left, #f033b5 2%, #f2a2af 82%);
    background: linear-gradient(to right, #f033b5 2%, #f2a2af 82%);
    filter: progid:DXImageTransform.Microsoft.gradient(startColorstr='#f033b5', endColorstr='#f2a2af', GradientType=1);
    -webkit-background-clip: text;
    background-clip: text;
    -webkit-text-fill-color: transparent;
}

.digital {
    color: white;
    font-weight: 700;
    font-size: 45px;
}

.dolor {
    font-size: 12px;
    color: white;


}


.scroll-down {
    color: white;
    font-size: 13px;
    text-decoration: none;
    cursor: pointer;
    position: absolute;
    top: 95%;
    left: 50%;
    transform: translate(-50%, -50%);

}

/*button bubble*/

.ball ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    cursor: pointer;
}

.ball ul li {
    background-color: #03a9f5;
    --c: white;
    color: var(--c);
    font-size: 12px;
    font-size: 14px;
    border-radius: 30px;
    text-align: center;
    position: relative;
    overflow: hidden;
    z-index: 2;
    transition: 0.5s;
    padding: 12px 20px;
    font-weight: 500;
    width: 150px;
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
    background-color: #611bca;
    color: black;
    border: 1px solid white;
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


/*rettangolo e cerchio*/
.cerchio {
    position: absolute;
    top: 30%;
    right: -200px;
    width: 350px;
}

.rettangolo {
    position: absolute;
    left: -350px;
    top: 0px;
    width: 550px;

}

@media only screen and (max-width: 768px) {

    #jumbo {
        padding: 0;
        
    }

    #jumbo img{
        padding-top: 70px;
    }


    .mouse-follower {
        display: none;
    }


    .fuksia,
    .digital {
        font-size: 30px;
    }

    .cerchio,
    .rettangolo {
        display: none;
    }

    .dolor br {
        display: none;
    }

    .dolor{
        font-size: 8px;
 
    }

    p.dolor{
        padding: 0;
        padding-bottom: 10px !important;
        margin: 0;
    }

    .scroll-down{
        font-size: 10px;
    }

}


</style>