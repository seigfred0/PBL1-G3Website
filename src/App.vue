<template>
  <div class="application">
    <!-- <router-link to="/">Home</router-link> | -->
    <Navigation></Navigation>
    <HomeViewVue></HomeViewVue>
  </div>
  <!-- <router-view/> -->
</template>

<script>
import Navigation from './components/Navigation.vue';
import HomeViewVue from './views/HomeView.vue';


export default {
  name: 'App',
  components: { HomeViewVue, Navigation }
}
</script>

<style>
#app {
  /* font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale; */
  font-family: var(--f-Noto);
  text-align: center;
  color: #2c3e50;
  border: 1px solid gray;
  height: 100vh;

  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

body {
  background: var(--backgroundColor);
  max-width: 550px;
  margin: 0 auto;
}


:root {
    --f-Noto : "Noto Sans Display", sans-serif;


    /* Colors */
    --backgroundColor: #0E0E0E;
    --textColor: #D0D0D0;
    --yellow: #EEDB63;


}

</style>
