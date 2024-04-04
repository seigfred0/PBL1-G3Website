<template>
<div class="wrapper">
  <div class="whiteBackground" v-show="overlay" ></div>

  <nav class="small-max ">
    <div class="logo">
        <h1>group<span>(three)</span></h1>
    </div>

    <div class="burger small-screen" @click="toggleMenu">
      <div class="line" :style="popUp"></div>
      <div class="line" :style="popUp"></div>
      <div class="line" :style="popUp"></div>
    </div>

    <div class="links small-screen" v-if="isMenuClicked">
        <ul> 
            <li ><a href="#">Home</a></li>
            <li ><a href="#">Contact</a></li>
            <li ><a href="#">About</a></li>
            <div class="cta small-screen">
                <button>Enroll Now</button>
            </div>
        </ul>
    </div>
    <div class="cta large-screen" >
        <ul> 
            <li ><a href="#">Home</a></li>
            <li ><a href="#">Contact</a></li>
            <li ><a href="#">About</a></li>
        </ul>
        <button>Enroll Now</button>
    </div>
  </nav>
</div>
</template>

<script>
export default {
    data() {
        return {
            isMenuClicked: false,
            overlay: false,
            popUp: null,
        }
    },
    methods: {
        toggleMenu() {
            
            this.isMenuClicked = !this.isMenuClicked
            if (this.isMenuClicked === true ) {
                this.overlay = true
                this.popUp = {backgroundColor: 'black'}
            } else {
                this.overlay = false
                this.popUp = {}
            }
           
        },
    }, 
    
}
</script>

<style>
.small-max {
    /* width: 100%; */
    /* max-width: 475px; */
    margin: 0 auto;
    padding-left: 1em;
    padding-right: 1em;
}

.small-max-absolute {
    top: 50%; 
    left: 50%; 
    transform: translate(-50%, -50%); 
}

nav {
    display: flex;
    justify-content: space-between;
    align-items: center;
    color: var(--textColor);
    position: relative;
    z-index: 1;


}

.links {
    display: flex;
    flex-direction: column;
    position: absolute;
  
    top: 0;
 
}

.wrapper {
    position: relative;
  
}

.whiteBackground {
    background-color: white;
      width: 100%;
    height: 100vh;
    z-index: 0;
    position: absolute;
  
}

.links ul li {
    font-size: 1.75rem;
    /* text-align: left; */
    /* background-color: red; */
     
}


.links {
    width: 100%;
    background-color: gray;
    margin-top: 4em;
}

.links ul{  
    display: flex;  
    flex-direction: column;
    position: absolute;
    list-style-type: none;
    gap: 3em;

    width: 100%;
    left: -0.5em;
    margin-top: 7em;
    /* background-color: gray; */
    padding: 0 0 0 0;
}

/* .links ul li{  
    width: 100%;

} */

.links ul a {
    color: var(--backgroundColor);
    text-decoration: none;
 
}


.line {
  width: 27px;
  height: 3px;
  background-color: rgb(218, 218, 218);
  margin: 4px 0;
}

.burger {
      cursor: pointer;

}

.line.black {
  background-color: rgb(0, 0, 0);
}



.cta.small-screen {
    border-top: 2px solid black;
    padding-top: 6em;

}

.cta.small-screen button {
    padding: 1em 2.5em;
    font-size: 1rem;
    cursor: pointer;
    background-color: var(--yellow);
    border: 1px solid gray;
    border-radius: 5px;

    font-family: var(--f-noto);
    font-weight: bold;
}

/* Responsive */
.large-screen {
    display: none;
}

.small-screen {
    display: block;
}

@media screen and (min-width: 560px) {
    .large-screen {
        display: block;
    }

    .small-screen {
        display: none;
    }
}
</style>