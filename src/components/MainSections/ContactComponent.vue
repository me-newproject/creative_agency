<template>
    <section id="contact">
        <div class="container">

            <div class="row">

                <div class="col-lg-7">

                    <div class="box">
                        <div class="row g-3">
                            <div class="title-form">
                                <h2>Get In Touch</h2>
                            </div>
                            <div class="col-md-5">
                                <div>
                                    <input class="form-control" id="your_name" name="userName" placeholder="Name"
                                        required="" type="text"
                                        style="width: 100%; height: 45px; margin-bottom: 25px;">
                                </div>

                                <div>
                                    <input class="form-control" id="your_email" name="userEmail" placeholder="Email"
                                        required="" type="email"
                                        style="width: 100%; height: 45px; margin-bottom: 25px;">
                                </div>
                                <div>
                                    <input class="form-control" id="subject" name="userSubject" placeholder="Subject"
                                        required="" type="text"
                                        style="width: 100%; height: 45px; margin-bottom: 25px;">
                                </div>
                            </div>
                            <div class="col-md-7">

                                <div>
                                    <textarea class="form-control" id="message" name="userMessage" placeholder="Message"
                                        style="width: 100%;  height: 183px; "></textarea>
                                </div>
                            </div>

                            <div class="container my-3">
                                <div class="row">
                                    <div class="col-lg-12 d-flex justify-content-center align-items-center">

                                        <div class="ball">
                                            <ul>
                                                <li>
                                                    <a>
                                                        Send Message
                                                        <span></span><span></span><span></span><span></span>
                                                    </a>
                                                </li>
                                            </ul>
                                        </div>
                                    </div>
                                </div>

                            </div>


                        </div>
                    </div>
                </div>
                <div class="col-lg-5 order-first order-sm-1">
                    <div class="box-location">


                        <div class="box-info d-flex">
                            <i class="fa-solid fa-location-dot"></i>
                            <div class="title-form pb-5">
                                <h2>Our Location</h2>
                                <p>There are many variations of passages of Lorem <br> Ipsum available, but the majority
                                    have suffered .</p>
                            </div>
                        </div>
                        <div class="b-info d-flex">
                            <i class="fas fa-map-pin"></i>
                            <div>
                                <p>123 Park Avenue, New York,United States</p>


                            </div>
                        </div>
                        <div class="b-info d-flex">
                            <i class="fas fa-phone"></i>
                            <div class="tel">
                                <a href="">+1 631 1234 5678</a>
                                <a href="">+1 631 1234 5678</a>
                            </div>
                        </div>
                        <div class="b-info d-flex">
                            <i class="fas fa-paper-plane"></i>
                            <div class="posta">
                                <a href="">email@website.com</a>
                                <a href="">abc@website.com</a>
                            </div>
                        </div>

                    </div>
                </div>
            </div>
        </div>
    </section>

</template>


<script>
export default {
    name: "ContactComponent",
}

</script>


<style scoped>
#contact {
    padding-top: 300px;
    padding-bottom: 100px;
}



.title-form h2 {
    font-weight: 600;
    font-size: 40px;
    color: #404854;
    padding-bottom: 20px;

}

.title-form p {
    line-height: 2;
    margin-bottom: 30px;
    font-weight: 250;
    font-family: "Roboto", sans-serif;
}

.form-control {
    font-family: "Roboto", sans-serif;
    font-size: 15px;
}

.form-control:focus {
    box-shadow: none;
    border-color: #d4d4d4;
}



.b-info i {
    font-size: 30px;
    color: #7004bc;
    margin-right: 20px;
    padding-bottom: 30px;

}


.b-info p,
.b-info a {
    font-weight: 300;
    font-family: "Roboto", sans-serif;
    color: #404854;

}



.tel a {
    text-decoration: none;
    color: #404854;
    padding-right: 10px;

}

.posta a {
    text-decoration: none;
    padding-right: 10px;
    color: #43bff7;
}


/*button bubble*/

.ball ul {
    list-style-type: none;
    margin: 0;
    padding: 0;
    cursor: pointer;
}

.ball ul li {
    background-color: #6f04bc;
    --c: #03a9f5;
    color: white;
    font-size: 14px;
    border: 2px solid transparent;
    border-radius: 50px;
    width: 609px;
    height: auto;
    font-weight: 600;
    font-family: sans-serif;
    letter-spacing: 0.1em;
    text-align: center;
    line-height: 3em;
    position: relative;
    overflow: hidden;
    z-index: 1;
    transition: 0.5s;
    margin: 1em;
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
    border: 2px solid #03a9f5;
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

    .ball ul li {
        width: 300px;

    }

    .box-location {
        margin-bottom: 20px;
    }

    .title-form p br {
        display: none;
    }

    .posta,
    .tel {
        display: flex;
        flex-direction: column;
    }

}
</style>