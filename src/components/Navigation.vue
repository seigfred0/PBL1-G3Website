<template>
  <nav>
    <!-- <div class="logo">
      <h1>Group(three)</h1>
    </div> -->
    <div class="logo">
      <h3>Group(three)</h3>
    </div>
  

    <div class="burger-icon" @click="toggleNav()">
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
    </div>

    <!-- Mobile Pop Up Nav -->
    <div v-show="mobileNav" class="overlay">
      <a v-on:click="toggleNav()" class="closebtn">&times;</a>
      <div class="overlay-content">
        <a href="#">About</a>
        <a href="#">Contact</a>
        <a href="#">Articles</a>
        <a href="#">Curriculum</a>
      </div>
    </div>


  </nav>
</template>

<script>
export default {
  data() {
    return {
      mobileNav: true,
    }
  },
  methods: {
    toggleNav() {
     this.mobileNav = !this.mobileNav
    }
  }

}
</script>

<style>

nav {
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding: 1em;
}

.logo h3 {
  font-size: 1.25rem;
  color: var(--textColor);
}


.overlay a{
  color: var(--textColor);
  text-decoration: none;

  display: block;
  transition: 0.9s opacity;
  font-size: 1.5rem;

}

.overlay {
  background-color: rgb(34, 34, 34);
  height: 100%;
  width: 100%;
  position: fixed;
  left: 0;
  top: 0;
  overflow-x: hidden;
  transition: opacity 0.5s ease-in-out;
}

.overlay-content {
  display: flex;
  flex-direction: column;
  gap: 1.5em;
  position: relative;
  top: 25%;
  width: 100%;
  text-align: left;
  margin-left: 3em;
  margin-top: 30px;

}

.overlay .closebtn {
  position: absolute;
  top: 20px;
  right: 30px;
  font-size: 50px;
  cursor: pointer;
}


/* Burger menu */
.burger-icon {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  width: 30px;
  height: 20px;
  cursor: pointer;
}

.line {
  width: 100%;
  height: 3px;
  background-color: #dadada;
  transition: transform 0.3s, opacity 0.3s;
}


/* .burger-icon.clicked .line:nth-child(2) {
  opacity: 0;
}


.burger-icon.clicked .line:nth-child(1) {
  transform: translateY(7px) rotate(45deg);
}

.burger-icon.clicked .line:nth-child(3) {
  transform: translateY(-7px) rotate(-45deg);
} */
</style>


<!-- 




 -->