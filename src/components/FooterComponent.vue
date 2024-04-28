<template>
    <section id="footer">
        <div class="container bg-light">
            <div class="row">
                <div class="col-md-6 d-flex justify-content-center align-items-center">
                    <div class="social-footer">
                        <a href="#"><i class="fab fa-facebook-f"></i></a>
                        <a href="#"><i class="fab fa-twitter"></i></a>
                        <a href="#"><i class="fab fa-google-plus-g"></i></a>
                        <a href="#"><i class="fab fa-linkedin-in"></i></a>
                        <a href="#"><i class="fab fa-instagram"></i></a>
                        <a href="#"><i class="fab fa-pinterest-p"></i></a>
                    </div>
                </div>
                <div class="p-footer col-md-6 d-flex justify-content-center align-items-center">
                    <p>© 2024 MegaOne. Made With Love By <a href="">Themesindustry</a></p>
                </div>
            </div>
        </div>
        <div>
            <button id="scrollUp" class="btn btn-primary rounded-pill" @click="scrollToTop"><i
                    class="fas fa-angle-up"></i></button>
        </div>




    </section>

</template>


<script>
export default {
    name: "FooterComponent",

    methods: {
        scrollToTop() {
            window.scrollTo({ top: 0, behavior: 'smooth' });
        }
    }

}


</script>


<style scoped>
#footer {
    background-color: #f8f9fa;
    padding: 80px;
    justify-content: center;
    align-items: center;
}

.social-footer a {
    display: inline-block;
    width: 30px;
    height: 30px;
    color: #696969;
    text-align: center;
    line-height: 30px;
    margin-right: 30px;
    font-size: 17px;

}

.social-footer a:hover {
    background-color: #00bcd4;
    border-radius: 100px;
    color: white;
}


.p-footer,
.p-footer a {
    letter-spacing: 0.2px;
    font-family: "Roboto", sans-serif;
    color: #696969;
    text-align: right;
    font-weight: 300;
    text-decoration: none;
    font-size: 14px;
}


.p-footer a:hover {
    color: #00bcd4;
}

#scrollUp {
    position: fixed;
    bottom: 20px;
    right: 20px;
    background-color: #643094;
    color: white;
    border: none;
    border-radius: 50%;
    width: 45px;
    height: 45px;
    text-align: center;
    font-size: 22px;
    cursor: pointer;


}

#scrollUp:hover {
    background-color: #00bcd4;
}


@media only screen and (max-width: 768px) {

    #footer {
        margin: 0;
        padding: 0;
    }

    .social-footer{
        padding: 20px;
    }

    .social-footer a {

        margin: 10px 5px;
        justify-content: space-around;

    }

    #footer .p-footer {
        margin-top: 25px;
        padding-bottom: 50px;
    }

}
</style>