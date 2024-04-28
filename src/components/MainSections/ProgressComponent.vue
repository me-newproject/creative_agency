<template>
  <section id="progress" class="my-5 py-5">
    <div class="container mt-5">
      <div class="row">

        <div class="col-lg-6">
          <img src="@/assets/letter-art-3.png" alt="desk" class="desk img-fluid">

        </div>

        <div class="col-lg-6 order-first order-sm-1">
          <div class="title mb-3">
            <h6>We are megaone company</h6>
            <h2>We have done some <br> great idea.</h2>

          </div>
          <div class="title-progress">
            <p class="par">There are many variations of
              passages of Lorem Ipsum available, but the majority have suffered
              alteration in some form, by injected. </p>
          </div>
          <div>
            <ul class="list-progress d-flex justify-content-between">
              <li><i class="fas fa-user"></i>
                <h6 class="counter">
                  {{ primoNumero }} +
                </h6>
                <p>Happy Clients</p>
              </li>
              <li><i class="fas fa-list"></i>
                <h6 class="counter">
                  {{ secondoNumero }} +
                </h6>
                <p>Lines Of Code</p>
              </li>
              <li><i class="fas fa-medal"></i>
                <h6 class="counter">
                  {{ terzoNumero }} +
                </h6>
                <p>Project Completed</p>
              </li>
            </ul>

          </div>
        </div>


      </div>



    </div>
  </section>

</template>


<script>
export default {
  name: "ProgressComponent",

  data() {
    return {
      primoNumero: 0,
      secondoNumero: 600,
      terzoNumero: 100,
      contatoreAvviato: false,
    };
  },
  mounted() {
    window.addEventListener('scroll', this.controllaScroll);
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.controllaScroll);
  },
  methods: {
    controllaScroll() {
      if (!this.contatoreAvviato && window.scrollY >= 500) { // Sostituisci il numero con il punto dello scroll desiderato
        this.avviaContatore();
        this.contatoreAvviato = true;
      }
    },
    avviaContatore() {
      const incrementoPrimo = setInterval(() => {
        if (this.primoNumero < 500) {
          this.primoNumero++;
        } else {
          clearInterval(incrementoPrimo);
        }
      }, 5); // tempo in millisecondi 0.0005s

      const incrementoSecondo = setInterval(() => {
        if (this.secondoNumero < 1074) {
          this.secondoNumero++;
        } else {
          clearInterval(incrementoSecondo);
        }
      }, 5);

      const incrementoTerzo = setInterval(() => {
        if (this.terzoNumero < 600) {
          this.terzoNumero++;
        } else {
          clearInterval(incrementoTerzo);
        }
      }, 5);
    },

  },
}

</script>


<style scoped>
#progress {

  background: linear-gradient(to right, #207efd, #03a9f5);
  color: white;
  padding: 110px;
}


#progress img {
  max-width: 100%;


}

.title h2 {
  font-size: 40px;
  font-weight: 700;
}

.title h6 {
  font-family: "Roboto", sans-serif;
  font-size: 18px;
}

.title-progress {
  line-height: 2;
  font-family: "Roboto", sans-serif;
  font-size: 17px;
  font-weight: 300;
}




.list-progress,
.list-progress i,
.list-progress h6 {
  list-style-type: none;
  font-size: 30px;
  padding-left: 0;
}

.list-progress p {
  font-size: 17px;
  font-weight: 500;
  font-family: "Roboto", sans-serif;

}

@media only screen and (max-width: 768px) {

  #progress {
    margin: 0;
    padding: 0;
  }

  .title,
  h2,
  .par {

    text-align: center;
  }


  .list-progress{
    text-align: center;
  }

  .list-progress h6{
    font-size: 22px;
  }

  .title h2{
    font-size: 30px;
  }



}
</style>