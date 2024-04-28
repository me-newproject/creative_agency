<template>
    <header class="fixed-top">



        <nav class="navbar navbar-expand-lg py-3"
            :class="{ 'fadeInDown': isNavBarVisible, 'fixed-top2': isNavBarFixed }" id="navbar">
            <div class="mouse-circle" :style="{ left: x + 'px', top: y + 'px' }"></div>


            <div class="container-fluid">

                <div>
                    <a class="hamburger" @click="openPanel" href="#"><i class="fas fa-bars"></i></a>

                </div>

                <div v-if="isPanelOpen" class="side-panel" id="modal-overlay">
                    <a class="closex" @click="closePanel">X</a>

                    <img src="@/assets/shape-8.png" alt="rettangolo" class="panel-image img-fluid" />


                    <ul class="mpanel">
                        <li><a href="#" @click="closePanel">Home
                                <span class="panel-circle"></span>
                            </a></li>
                        <li><a href="#about" @click="closePanel">About
                                <span class="panel-circle"></span>
                            </a></li>
                        <li><a href="#work" @click="closePanel">Work
                                <span class="panel-circle"></span>
                            </a></li>
                        <li><a href="#clients" @click="closePanel">Clients
                                <span class="panel-circle"></span>
                            </a></li>
                        <li><a href="#blog" @click="closePanel">Blog
                                <span class="panel-circle"></span>
                            </a></li>
                        <li><a href="#contact" @click="closePanel" class="contact">Contact
                                <span class="panel-circle"></span>
                            </a></li>

                    </ul>


                    <div class="shape-right">
                        <div class="right-panel">
                            <h6 class="press-contact">Press Contact</h6>
                            <p ><i class="fas fa-user-alt"></i> David Warrior</p>
                            <p><i class="fas fa-mobile-alt"></i>36 78 24 49 53 97+ </p>
                            <p ><i class="fas fa-envelope"></i>contact@megaone.com</p>
                        </div>
                        <img src="@/assets/shape-7.png" alt="cerchio" class="panel-imagedue img-fluid" />

                    </div>

                </div>

                <div>

                    <img class="logom" src="@/assets/logo-white.png" alt="logo-megaone">

                </div>

                <button class="navbar-toggler custom-toggler" type="button" data-bs-toggle="collapse"
                    data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent"
                    aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                </button>

                <div class="collapse navbar-collapse" id="navbarSupportedContent">

                    <div class="container">
                        <ul class="navbar-menu navbar-nav">
                            <li class="nav-item me-1">
                                <a class="nav-link home sottolineato " aria-current="page" href="#">Home</a>


                            </li>
                            <li class="nav-item me-1">
                                <a class="nav-link sottolineato" href="#about">About us</a>

                            </li>
                            <li class="nav-itemme-1 ">
                                <a class="nav-link sottolineato" href="#work">Our Work</a>

                            </li>
                            <li class="nav-item me-1">
                                <a class="nav-link sottolineato" href="#clients">Clients</a>

                            </li>
                            <li class="nav-item me-1 ">
                                <a class="nav-link sottolineato" href="#blog">Our Blog</a>

                            </li>
                            <li class="nav-item me-1 ">

                                <a class="nav-link sottolineato" href="#contact">Contact Us</a>
                            </li>
                        </ul>
                    </div>
                </div>

                <div class="ball">
                    <ul>
                        <li>
                            <a @click="showModal">Get A Quote
                                <span></span><span></span><span></span><span></span>
                            </a>
                        </li>
                    </ul>
                </div>

                <div class="ico-nav mx-3">
                    <i class="fab fa-facebook-f mx-3"></i>
                    <i class="fab fa-instagram mx-3"></i>
                    <i class="fab fa-twitter mx-3"></i>
                </div>
            </div>
        </nav>
    </header>

    <!-- inizio modale -->
    <div class="modal-backdrop" v-show="isModalVisible">
        <div class="modal">
            <span class="pre-title text-center pt-5">We are megaone company</span>
            <div class="text-center">
                <h2 class="titlem">Lets start your <span style="color: #03a9f5;">project</span></h2>
                <button type="button" class=" btn btn-close" data-bs-dismiss="modal" aria-label="Close"
                    @click="closeModal"></button>
            </div>
            <div class="modal-body">

                <div class="form">
                    <div class="row">
                        <div class="col-md-6">
                            <input type="text" class="form-control mb-3" placeholder="Name" aria-label="Name">
                            <input type="text" class="form-control mb-3" placeholder="Contact #" aria-label="Contact">
                            <input type="text" class="form-control mb-3" placeholder="Project Type"
                                aria-label="Project">
                        </div>
                        <div class="col-md-6">
                            <input type="email" class="form-control mb-3" placeholder="Email" aria-label="Email">
                            <input type="text" class="form-control mb-3" placeholder="City/Country" aria-label="City">
                            <input type="text" class="form-control mb-3" placeholder="Budget" aria-label="Budget">
                        </div>
                        <div class="col-12 text-start">
                            <textarea class="form-control" id="exampleFormControlTextarea1" rows="4"
                                placeholder="Please explain your project in detail."></textarea>
                        </div>
                        <div class="col-12">
                            <div class="form-check d-flex justify-content-center align-items-center">
                                <input class="form-check-input" type="checkbox" id="gridCheck">
                                <label class="form-check-label" for="gridCheck">
                                    Contact by phone is preferred
                                </label>
                            </div>
                        </div>

                    </div>
                    <div class="modal-footer">

                    </div>

                </div>
            </div>

        </div>

        <div class="ball-message ">
            <ul>
                <li>
                    Send Message
                    <span></span><span></span><span></span><span></span>
                </li>
            </ul>
        </div>


    </div>

    <!-- fine modale -->

</template>


<script>
export default {
    name: "HeaderComponent",
    data() {
        return {
            isPanelOpen: false,
            isModalVisible: false,
            isNavBarVisible: false,
            isNavBarFixed: false,
            x: 0,
            y: 0,
        };
    },
    mounted() {
        window.addEventListener('scroll', this.handleScroll);
        window.addEventListener('mousemove', this.updatePosition);
    },
    beforeUnmount() {
        window.removeEventListener('scroll', this.handleScroll);
        window.removeEventListener('mousemove', this.updatePosition);
    },
    methods: {
        openPanel() {
            this.isPanelOpen = true;
            this.disableScroll();
        },
        closePanel() {
            this.isPanelOpen = false;
            this.enableScroll();
        },
        showModal() {
            this.isModalVisible = true;
        },
        closeModal() {
            this.isModalVisible = false;
        },

        disableScroll() {
            document.body.style.overflow = 'hidden';
            document.body.style.height = '100%';
        },
        enableScroll() {
            document.body.style.overflow = '';
            document.body.style.height = '';
        },

        handleScroll() {
            if (window.scrollY > 200) {
                this.isNavBarVisible = true;
                this.isNavBarFixed = true;
            } else {
                this.isNavBarVisible = false;
                this.isNavBarFixed = false;
            }
        },
        updatePosition(e) {
            const navbar = document.getElementById('navbar');
            const rect = navbar.getBoundingClientRect();
            const x = e.clientX - rect.left;
            const y = e.clientY - rect.top;

            // Verifica se il mouse è all'interno della navbar
            if (x >= rect.left && x <= rect.right && y >= rect.top && y <= rect.bottom) {
                // Calcola le coordinate per centrare il cerchio sotto il cursore all'interno della navbar
                const circleX = x - rect.left - 40; // 40 è metà della larghezza del cerchio (80/2)
                const circleY = y - rect.top - 40; // 40 è metà dell'altezza del cerchio (80/2)

                // Aggiorna la posizione del cerchio del mouse all'interno della navbar
                this.x = circleX;
                this.y = circleY;
            } else {
                // Se il mouse esce dalla navbar, reimposta le coordinate del cerchio fuori dalla navbar
                this.x = -100; // O una qualsiasi posizione che non sia visibile
                this.y = -100; // O una qualsiasi posizione che non sia visibile
            }
        }

    },

};



</script>


<style scoped>
/*cerhio che segue il mouse*/
.mouse-circle {
    position: absolute;
    width: 80px;
    height: 80px;
    border-radius: 50%;
    background: rgba(255, 255, 255, 0.071);
    pointer-events: none;
}

/*scroll navbar*/
.navbar {
    transition: all 0.3s ease-in-out;
}

.fadeIn {
    opacity: 1;
}

.fadeInDown {
    opacity: 1;
    transform: translateY(0);
}

.fixed-top2 {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    z-index: 9999;
    background: linear-gradient(to left, #3264f5 2%, #7004bc 82%);
    margin: 0;
    -webkit-box-shadow: 0px 2px 13px -6px #000000;
    -moz-box-shadow: 0px 2px 13px -6px #000000;
    -o-box-shadow: 0px 2px 13px -6px #000000;
    box-shadow: 0 10px 10px -10px rgba(0, 0, 0, 0.35);
    animation: slideDown 0.9s forwards;
}

@keyframes slideDown {
    from {
        top: -100px;
    }

    to {
        top: 0;
    }
}

/*side-panel*/

#modal-overlay {
    position: fixed;
    top: 0;
    left: 0;
    width: 100vw;
    height: 100vh;
    background-color: rgba(0, 0, 0, 0.91);
    z-index: 9999;
}

.side-panel {
    position: fixed;
    left: 0;
    top: 0;
    width: 60%;
    height: 100%;
    padding: 20px; 
}

.side-panel ul li {
    display: flex;
    margin-bottom: 50px;
    clear: both;
    list-style-type: none;
}

.side-panel ul>li>a:before {
    content: "";
    width: 2px;
    height: 100%;
    position: absolute;
    background-color: #FFFFFF;
    opacity: .5;
    transform: translateX(-20px);
    top: 26px;
}

.contact:before {
    display: none;
}

.panel-circle {
    content: "";
    position: absolute;
    border: 1px solid #FFFFFF;
    border-radius: 100%;
    overflow-x: hidden;
    width: 10px;
    height: 10px;
    left: 0;
    right: auto;
    transform: translateX(-24px);
    top: 15px;
}


ul>li>a:hover .panel-circle {
    background-color: white;
}


.panel-image {
    top: 0;
    left: 0;
    width: 65%;
    height: auto;
    object-fit: cover;
    object-position: -300px -200px;
    position: fixed;
    z-index: -2;
    
}

.panel-imagedue {
    top: 0;
    transform: translate(1000px, 100px);
    width: 400px;
    object-fit: cover;
    position: fixed;
    z-index: -2;
}





.closex {
    font-size: 30px;
    color: white;
    text-decoration: none;
    cursor: pointer;
    position: fixed;
    z-index: 3;
    transform: translate(50px, 50px);

}



.mpanel li a {
    z-index: 2;
    position: fixed;
    transform: translate(150px, 60px);
    cursor: pointer;
    font-size: 25px;
    letter-spacing: 2px;
    font-weight: 200;
    color: white;
    text-decoration: none;
}

.right-panel {
    z-index: 2;
    position: fixed;
    transform: translate(1050px, -100px);
    cursor: pointer;
    font-size: 12px;
    letter-spacing: 2px;
    font-weight: 200;
    color: white;
    direction: rtl ; /*right to left il pannello si visiona al contrario*/
    margin-inline-end: -10px; /* Spazio che si comporta come margin-left in un panel rtl*/
}


.right-panel p i {
    margin-inline-end: 10px; /* Spazio tra l'icona e il testo  si comporta come margin-left in un panel rtl*/
}



.press-contact{
    padding: 20px 0;
}


.press-contact:after{
    content: "";
    margin-top: 10px;
    height: 3px;
    position: absolute;
    width: 35px;
    top: auto;
    left: auto;
    background: #FFFFFF;
    display: block;
}




/*icona hamburger*/

.hamburger i {
    color: white;
    padding: 0 25px;
    font-size: 25px;
}

/*navbar*/

.fixed-top {

    background: linear-gradient(to right, #3264f5 2%, #7004bc 82%);
    position: fixed;

}


nav ul li a {
    color: white;
    font-size: 14px;
    display: block;

}

nav ul li a:hover {
    color: white;

}

.nav-link.home {
    color: white;
    /* Colore del link quando non è attivo */
}


.navbar-menu {
    display: flex;
    justify-content: flex-end;
}


.logom {
    width: auto;
    height: 27px;
}



.ico-nav {
    color: white;
    cursor: pointer;
}


.ico-nav i:hover {
    color: #f021b6;
}

/*sottolineatura link-menu */
.sottolineato {
    position: relative;
}

.sottolineato::before {
    content: "";
    position: absolute;
    left: 0;
    bottom: 0;
    width: 100%;
    height: 2px;
    background-color: white;
    transform: scaleX(0);
    transition: all 0.4s;
}

.sottolineato:hover::before {
    transform: scaleX(1);
}




/*inizio button bubble*/

.ball ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    cursor: pointer;

}

.ball ul li {
    --c: white;
    color: var(--c);
    background-color: transparent;
    font-size: 14px;
    border: 2px solid var(--c);
    border-radius: 30px;
    text-align: center;
    position: relative;
    overflow: hidden;
    z-index: 2;
    transition: 0.5s;
    padding: 10px 20px;
    font-weight: 500;

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
    color: black;
    border: 2px solid white;
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


/*inizio modale get a quote*/
.pre-title {
    color: #696969;
    font-size: 18px;
    font-family: "Roboto", sans-serif;

}

.titlem {
    font-size: 40px;
    font-weight: 600;
    color: #404854;
    margin-top: 15px;

}




.modal-backdrop {
    position: fixed;
    background-color: rgba(240, 238, 245, 0.497);
    display: flex;
    justify-content: center;
    align-items: center;
    padding-top: 50px;
    padding-bottom: 20px;
    overflow-y: auto;
    overscroll-behavior: contain;
    /* Previene lo scorrimento della pagina principale */


}

/* nasconde le frecce dello scroll */
.modal {
    scrollbar-width: none;
    /* Firefox */
}

.modal::-webkit-scrollbar {
    display: none;
    /* Chrome, Safari, Opera */
}

.modal {
    background: #FFFFFF;
    display: flex;
    flex-direction: column;
    width: 900px;
    margin: 30px;
    position: relative;
    overflow-y: scroll;
    /*fa scrollare lo stesso la modale*/
    z-index: 0;

}


.modal-footer {
    padding-top: 45px;
    display: flex;
    justify-content: center;
    flex-direction: column;
    border-top: none;

}



.modal-body {
    border-top: none;
    border-bottom: none;
    font-family: "Roboto", sans-serif;
    position: relative;
    padding: 40px 100px;
}


/*form*/

.form-control {
    border-radius: 0;
    box-shadow: none;
    border: solid #d4d4d4;
    border-width: 0 0 1px 0;
    margin: 0 auto;
    padding: 10px;
    color: #d4d4d4;
    font-size: 14px;
    font-weight: 300;
    letter-spacing: 1px;
}

.form-control:focus {
    box-shadow: none;
    border-color: #d4d4d4;
}

.form-check {
    margin-top: 50px;
}

.form-check-label {
    color: #7c7c7c;
    font-size: 14px;
    font-weight: 400;
    letter-spacing: 1px;
    margin-left: 10px;
}

.form-check-input {
    border-radius: none;
    width: 25px;
    height: 25px;

}

.form-check-input:checked {
    background-color: #52c7e1;


}

.form-check-input:focus {
    box-shadow: none;
    border-color: #d4d4d4;
    border-radius: none;

}


/*modal btn*/


.btn-close {
    position: absolute;
    border: none;
    padding: 16px;
    cursor: pointer;
    background: #f309b0;
    border-radius: 50px;
    top: 15px;
    right: 15px;
    width: 10px;
    height: 10px;
    --bs-btn-close-opacity: none;
}

.btn-close::after,
.btn-close::before {
    content: '';
    position: absolute;
    top: 50%;
    left: 50%;
    width: 20px;
    height: 2px;
    background-color: #fff;
}

.btn-close:before {
    transform: translate(-50%, -50%) rotate(45deg);
}

.btn-close:after {
    transform: translate(-50%, -50%) rotate(-45deg);
}

.btn-close:hover {
    color: white;
    background: #03a9f5;
}

/*button ball message*/
.ball-message {
    position: absolute;
    bottom: -5px;
    z-index: 1000;


}

.ball-message ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    cursor: pointer;

}

.ball-message ul li {
    background-color: #03a9f5;
    --c: #f021b6;
    color: white;
    font-size: 15px;
    border-radius: 50px;
    text-align: center;
    position: relative;
    overflow: hidden;
    z-index: 2;
    transition: 0.5s;
    padding: 12px 24px;
    font-weight: 500;
    width: 180px;
    height: auto;
    border: 1px solid transparent;

}

.ball-message ul li span {
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

.ball-message ul li:hover {
    background-color: white;
    color: white;
    border: 1px solid #f021b6;
}

.ball-message ul li:hover span {
    transform: translateY(0) scale(2);
}

.ball-message ul li span:nth-child(1) {
    --n: 1;
}

.ball-message ul li span:nth-child(2) {
    --n: 2;
}

.ball-message ul li span:nth-child(3) {
    --n: 3;
}

.ball-message ul li span:nth-child(4) {
    --n: 4;
}

@media only screen and (max-width: 768px) {

    .mouse-circle {
        display: none;
    }

    .hamburger {
        display: none;
    }

    .custom-toggler.navbar-toggler {
        border-color: white;
        color: white;
        

    }

    .navbar-toggler-icon {
        background-image: url("data:image/svg+xml,%3csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 30 30'%3e%3cpath stroke='white' stroke-linecap='round' stroke-miterlimit='10' stroke-width='2' d='M4 7h22M4 15h22M4 23h22'/%3e%3c/svg%3e");
        
    }

    .ball,
    .ico-nav {
        display: none;
    }


    /*.navbar>.container-fluid{
        justify-content: flex-start;
    }*/




}
</style>