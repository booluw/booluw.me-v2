<template>
  <div class="jumbotron" ref="jumbo">
    <div>
      <img alt="Picture of Boluwatife Johnson" src="../assets/me.png" class="jumbotron__img" ref="img">
    </div>
    <div class="jumbotron__text">
      <div id="text" ref="text">
        <span class="jumbotron__heading--small">I am</span>
        <h1 class="jumbotron__heading--lead">Boluwatife Johnson,</h1>
      </div>
      <p class="cover-letter" ref="cover_letter">
        FrontEnd Engineer, VUE JS junior and Technology writter.
      </p>
    </div>
    <div class="jumbotron__links" ref="links">
      <a href="//github.com/booluw" target="_blank" rel="noreferral">
        <i class="ion icon ion-logo-github"></i>
      </a>
      <a href="//twitter.com/booluw" target="_blank" rel="noreferral">
        <i class="ion icon ion-logo-twitter"></i>
      </a>
      <a href="//linkedin.com/in/johnson-boluwatife-8129b9110" target="_blank" rel="noreferral">
        <i class="ion icon ion-logo-linkedin"></i>
      </a>
    </div>
    <div class="jumbotron__border">
      <div style="flex-basis: 30%; background-color: #2e0854;"></div>
      <div style="flex-basis: 25%; background-color: #ffcb05;"></div>
      <div style="flex-basis: 20%; background-color: #004e89;"></div>
      <div style="flex-basis: 20%; background-color: #5eb1bf;"></div>
    </div>
  </div>
</template>

<script>
import { TimelineLite,Back,Bounce } from 'gsap'


export default {
  name: 'HelloWorld',
  mounted() {
    
    const tl = new TimelineLite()
    const jumbo = this.$refs.jumbo
    const img = this.$refs.img
    const text = this.$refs.text
    const cover_letter =  this.$refs.cover_letter
    const links =  this.$refs.links



    //    element, duration, {Properties to animate}
    tl.to(jumbo, 2, {scale: 1, opacity: 1, ease: Back.easeOut.config(1.7)})
    tl.to(text, 1, {y: 0,opacity: 1, ease: Back.easeOut.config(1.7)})
    tl.to(cover_letter, 0.5,{opacity: 1, x: 0})
    tl.to(img, 1, {x: 0,opacity: 1})
    tl.to(links, 2, {rotate: 0, ease: Bounce.easeOut})

  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
$base: #2e0854;
$secondary: #ffcb05;
$grey: #004e89;
$bg: #bbdef0;
$color: #5eb1bf;

#text {
  opacity: 0;
  transform: translateY(-20px);
}

.jumbotron {
  background-color: #264658;
  height: 60vh;
  display: flex;
  align-items: flex-start;
  padding: 0 .5rem;
  margin: 0 0 1.5rem;
  position: relative;

  transform: scale(.3);
  opacity: 0;

  &__img {
    width: 100%;
    height: 100%;
    margin: 3rem 0 0;
    background-color: #264658;
    border-radius: .5rem 0;
    text-align: right;

    opacity: 0;
    transform: translateX(-100px);
  }

  &__text {
    color: $grey;
    flex-basis: 60%;
    margin: 3rem 1rem 0;
  }

  &__heading {

    &--lead {
      padding: 0;
      margin: 0;
      color: white;
      font-family: Lora, serif;
    }

    &--small {
      font-size: 1.3rem;
      color: $color;
      font-family: Roboto, sans-serif;
    }
  }

  &__links {
    position: absolute;
    bottom: 15%;
    left: 37%;
    right: 0;
    display: flex;
    justify-content: space-around;

    padding: 0 .5rem 0 0;
    font-size: 2.5rem;

    transform: rotate(90deg);
    transform-origin: right;

    a {
      color: $color;
      transition: .3s ease-in-out;
      transform-origin: center;

      &:hover {
        transform: scale(1.2);
        color: $bg;
      }
    }
  }

  &__border {
    position: absolute;
    bottom: 0;
    right: 0;
    left: 0;
    height: .2rem;
    background-color: $bg;

    display: flex;
  }
}

.cover-letter {
  color: $secondary;
  font-kerning: auto;
  font-style: italic;
  font-family: Roboto, sans-serif;

  opacity: 0;
  transform: translateX(100px);
}

.cover-skills {
  display: flex;
  flex-wrap: wrap;
}

@media (min-width: 1200px) {
  .jumbotron {
    height: 80vh;
    padding: 0 4rem;
    align-items: stretch;

    &__img  {
      height: 80%;
      border: none;
    }

    &__text {
      margin: 4.5rem 1rem 0;
      font-size: 1.5rem;
      flex-basis: 40%;
    }

    &__heading {

      &--lead {
        font-size: 4rem;
      }

      &--small {
        font-size: 1.5rem;
      }
    }

    &__links {
      left: 80%;
      right: 4rem;
      padding: 0;
    }
  }
}
</style>
