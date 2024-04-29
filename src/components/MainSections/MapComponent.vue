<template>
    <section id="map">
        <div class="container">
            <div class="envato-slider d-flex" id="slider">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
                <img src="@/assets/client-4.png" alt="" srcset="">
            </div>
        </div>
        <div class="google-maps d-flex justify-content-center align-items-center">
            <iframe
                src="https://www.google.com/maps/embed?pb=!1m14!1m8!1m3!1d12097.433213460943!2d-74.0062269!3d40.7101282!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x0%3A0xb89d1fe6bc499443!2sDowntown+Conference+Center!5e0!3m2!1smk!2sbg!4v1539943755621"
                frameborder="0" style="border:0; width: 70%; height: 500px;" allowfullscreen=""></iframe>
        </div>
    </section>

</template>


<script>
export default {
    name: "MapComponent",
}

</script>


<style scoped>
/*envato slider*/

#map {
    background: linear-gradient(to right, #207efd, #03a9f5);
    height: 600px;
}

.container {
    width: 80%;
    height: 333px;
    overflow: hidden;
    position: relative;
    display: flex;
    justify-content: center; 
    align-items: center; 

}


.envato-slider img {
    margin-right: 100px;
    animation: slide 4s linear infinite;
}




@keyframes slide {
    0% {
        transform: translate3d(0);
    }

    25% {
        transform: translate3d(-240px, 0px, 0px);
    }

    50% {
        transform: translate3d(-240px, 0px, 0px);
    }

    75% {
        transform: translate3d(-240px, 0px, 0px);
    }

    100% {
        transform: translate3d(-240px, 0px, 0px);
    }
}

.google-maps {
    display: flex;
    justify-content: center;
    align-items: center;
}


@media only screen and (max-width: 768px) {
    

    .envato-slider img{
        margin: 0 60px;
    }
}
</style>