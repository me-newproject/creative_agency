<template>
    <section id="staff" class="my-5 py-5">
        <div class="container my-5">
            <div class="row">

                <div class="col-lg">
                    <div class="title mb-3">
                        <h6>We are megaone company</h6>
                        <h2>We have some <span class="word" style="color: #03a9f5;"
                                :class="{ 'capriola': cambiaParola }">
                                {{ parola }}</span></h2>
                        <h2>talented staff</h2>
                    </div>
                    <div class="title-progress">
                        <p class="par">There are many variations of
                            passages of Lorem Ipsum available, <br>but the majority have suffered
                            alteration in some form, by injected. </p>
                    </div>

                </div>
            </div>
        </div>

        


        <div class="container">
            <div class="row">

                <div class="col-lg-4 d-flex flex-column justify-content-center align-items-center">
                    <div class="team-item">
                        <img alt="image" class="team-image" src="@/assets/team-img1.png">                      
                        <div class="name">
                            <img alt="shape" src="@/assets/shape-10.png">
                            <h6>David Joe</h6>
                        </div>
                    </div>
                    
                    <p class="craft" >Director</p>
                    <div class="social">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                    </div>
                    
                </div>
                <div class="col-lg-4 d-flex flex-column justify-content-center align-items-center">
                    <div class="team-item">
                       
                        <img alt="image" class="team-image" src="@/assets/team-img2.png">
                        
                        <div class="name">
                            <img alt="shape" src="@/assets/shape-9.png">
                            <h6>Natalie Roy</h6>
                        </div>

                    </div>
                    <p class="craft"  >Director</p>
                    <div class="social">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
                <div class="col-lg-4 d-flex flex-column justify-content-center align-items-center">
                    <div class="team-item">
                        <img alt="image" class="team-image" src="@/assets/team-img3.png">                  
                        <div class="name">
                            <img alt="shape" src="@/assets/shape-11.png">
                            <h6>Jhon Wok</h6>
                        </div>
                    </div>
                    <p class="craft">Director</p>
                    <div class="social">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                    </div>
                </div>
            </div>
        </div>

    </section>

</template>


<script>
export default {
    name: "StaffComponent",
    data() {
        return {
            parola: 'ideal',
            parole: ['ideal', 'great'],
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


/*animazioni*/

@keyframes pulse {
    0% {
        transform: scale(0.95);
    }

    70% {
        transform: scale(1);

    }

    100% {
        transform: scale(0.95);

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


/* team */

.team-item {
    cursor: pointer;
    position: relative;
}

.team-item .team-image {
    max-width: 250px;
    display: inline-block;
    margin-bottom: 30px;
    
}

.team-item:hover .team-image {
    -webkit-animation: 1s pulse;
    -o-animation: 1s pulse;
    animation: 1s pulse;
}

.team-item .name {
    position: relative;
}

.team-item  {
    position: relative;
    -webkit-transition: all .3s ease-in-out;
    -moz-transition: all .3s ease-in-out;
    -ms-transition: all .3s ease-in-out;
    -o-transition: all .3s ease-in-out;
    transition: all .3s ease-in-out;
}

.team-item:hover  {
    transform: translateY(5px);
    -webkit-transition: all .3s ease-in-out;
    -moz-transition: all .3s ease-in-out;
    -ms-transition: all .3s ease-in-out;
    -o-transition: all .3s ease-in-out;
    transition: all .3s ease-in-out;
}

.team-item .name>h6 {
    font-size: 23px;
    margin: 0;
    position: absolute;
    width: 100%;
    top: 50%;
    font-weight: 400;
    transform: translateY(-50%);
    text-align: center;
    -webkit-transition: all .3s ease-in-out;
    -moz-transition: all .3s ease-in-out;
    -ms-transition: all .3s ease-in-out;
    -o-transition: all .3s ease-in-out;
    transition: all .3s ease-in-out;
}

.team-item .name>img {
    opacity: 0;
    -webkit-transition: all .3s ease-in-out;
    -moz-transition: all .3s ease-in-out;
    -ms-transition: all .3s ease-in-out;
    -o-transition: all .3s ease-in-out;
    transition: all .3s ease-in-out;
}

.team-item:hover .name>img {
    opacity: 1;
}

.team-item:hover .name>h6 {
    color: #fff;
}

.team-item  a i {
    display: inline-block;
    width: 35px;
    height: 35px;
    text-align: center;
    line-height: 35px;
    border-radius: 50px;
    font-size: 17px;
    margin-right: 1px;
    color: #3b3b3b;
    border: 1px solid transparent;
    -webkit-transition: background-color .2s ease-in-out;
    -moz-transition: background-color .2s ease-in-out;
    -ms-transition: background-color .2s ease-in-out;
    -o-transition: background-color .2s ease-in-out;
    transition: background-color .2s ease-in-out;
}

.team-item  a i:hover {
    color: #fff;


    
}

.craft  {
    font-family: "Roboto", sans-serif;
    font-weight: 300;
    margin-top: 10px;
}

/*social*/
.social a {
    display: inline-block;
    width: 30px;
    height: 30px;
    color: black;
    text-align: center;
    line-height: 30px;
    margin-right: 10px;
}

.social a:hover {
    background-color: #316ab5;
    border-radius: 100px;
    color: white;
}

@media only screen and (max-width: 768px) {

#staff {
  margin: 0;
  padding: 0;
}

.title,
h2,
.par {

  text-align: center;
}


.title-progress br{
  display: none;
}

.title h2{
  font-size: 30px;
}

.social a{
    margin-bottom: 20px;
}



}



</style>