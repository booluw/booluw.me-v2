<template>
  <div class="jumbotron">
    <div class="jumbotron__social">
      <img alt="Picture of Boluwatife Johnson" src="../assets/me.png" class="jumbotron__img">
    </div>
    <div class="jumbotron__text">
      <div>
        <span class="jumbotron__heading--small">I am</span>
        <h1 class="jumbotron__heading--lead">Boluwatife Johnson,</h1>
      </div>
      <p class="cover-letter">
        I'm passionate about building responsive and interactive websites.
      </p>
      <!--div class="cover-skills">
        <div class="chip">HTML</div>
        <div class="chip">CSS</div>
        <div class="chip">JavaScript</div>
        <div class="chip">Vue JS</div>
        <div class="chip">Sass</div>
      </div -->
    </div>
    <div class="jumbotron__links">
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
export default {
  name: 'HelloWorld',
  props: {
    msg: String
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

.jumbotron {
  background-color: $base;
  height: 60vh;
  display: flex;
  align-items: flex-start;
  padding: 0 .5rem;
  position: relative;

  &__social {
    flex-basis: 40%;
    height: 45%;
    margin: 3rem 0 0;
    padding: .5rem;
    box-sizing: border-box;
    background-color: $base;
    border: .2rem solid $bg;
    border-radius: .5rem 0;
    text-align: right;
  }

  &__img {
    width: 80%;
    height: 100%;
    transform: rotate(10deg);
  }

  &__text {
    color: $grey;
    flex-basis: 60%;
    margin: 3rem 1rem 0;
    //align-self: center;
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

    &__social  {
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
