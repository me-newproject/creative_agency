<template>
  <HeaderComponent/>
  <JumboComponent/>
  <MainComponent/>
  <FooterComponent/>

</template>

<script>
import HeaderComponent from './components/HeaderComponent.vue'
import JumboComponent from './components/JumboComponent.vue'
import MainComponent from './components/MainComponent.vue'
import FooterComponent from './components/FooterComponent.vue'

export default {
  name: 'App',
  components: {
    HeaderComponent,
    JumboComponent,
    MainComponent,
    FooterComponent
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Montserrat:ital,wght@0,100..900;1,100..900&display=swap');
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap');


*{ 
  margin: 0;
  padding: 0;
  box-sizing: border-box;

}

#app {
  font-family:  "Montserrat", sans-serif;
  overflow-x: hidden;
}


</style>
