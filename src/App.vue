<template>
  <div id="app">
    <app-header />
    <router-view />
    <app-footer />
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'
import AppFooter from '@/components/AppFooter.vue'

export default {
  name: 'App',
  components: {
    'app-header': AppHeader,
    'app-footer': AppFooter
  }
}
</script>

<style lang="scss">
@font-face {
  font-family: Lora;
  src: url('assets/fonts/Lora-Regular.ttf');
  font-weight: 400;
}
@font-face {
  font-family: Lora;
  src: url('assets/fonts/Lora-Bold.ttf');
  font-weight: bold;
}
@font-face {
  font-family: Roboto;
  src: url('assets/fonts/Roboto-Regular.ttf');
  font-weight: 400;
}
@font-face {
  font-family: Roboto;
  src: url('assets/fonts/Roboto-Medium.ttf');
  font-weight: 500;
}
@font-face {
  font-family: Roboto;
  src: url('assets/fonts/Roboto-Bold.ttf');
  font-weight: bold;
}


$base: #2e0854;
$secondary: #ffcb05;
$grey: #004e89;
$bg: #bbdef0;
$color: #5eb1bf;

body {
  font-family: Roboto, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  padding: 0;
  margin: 0;
  background-color: $bg;
  color: #264658;
}

.section {
  padding: 1rem .5rem;
  background-color: $bg;
}

.slider {
  display: flex;
  overflow-x: auto;
  margin: 3rem 0 .5rem 0;
  padding: 0 1rem 1rem 0;
}

.container {

  &--flex {
    display: flex;
    flex-wrap: wrap;
  }
}

.heading {
  font-family: Lora;
  padding: 0;
  margin: 0;
  font-variant: small-caps;
  font-size: 2.3rem;
  
  &--small {
    font-variant: normal;
    text-transform: uppercase;
    font-size: 1.3rem;
    text-shadow: 0px 0px 2px black;
    letter-spacing: .2rem;
  }

}

.chip {
  margin: 0 1rem 0 0;
  -webkit-margin-top-collapse: collapse;
  font-weight: 500;
  text-transform: uppercase;
}

.card {
  position: relative;
  min-width: calc(100% / 1.1);

  background-color: $bg;
  cursor: pointer;
  border-top: .3rem solid #264658;
  border-radius: .5rem;
  padding: 0 0 1rem;
  margin: 0 .3rem;
  box-shadow: 5px 5px 10px rgba($color: $base, $alpha: .5);

  display: flex;
  flex-direction: column;
  justify-content: flex-start;

  &--with-img {

    &:hover .card__img {
      filter: grayscale(0);
    }
    .card__img {
      width: 100%;
      height: auto;
      filter: grayscale(100%);
      transition: .5s ease;
      border-radius: .1rem;
    }
  }

  &--experience {
    width: auto;
    border-top: none;
    border-left: .5rem solid #264658;
    margin: .7rem 1.8rem .7rem 1rem;
    padding: 2rem 0;

    .card__icon {
      position: absolute;
      left: -1.8rem;
      top: .7rem;
      
      background-color: #264658;
      color: $bg;
      padding: .8rem 1rem;
      border-radius: 50%;
      font-size: 1.5rem;
    }

    .card__description {
      margin: 1rem 0 0;
    }
  }

  &--recommendation {
    border-top: none;
    padding: 1rem .5rem;

    background: linear-gradient(to bottom, white 64%, crimson 46%);
    text-align: center;

    .card__img {
      border-radius: 50%;
      width: 8rem;
      height: 8rem;
      border: .5rem solid white;
    }
    .card__description {
      text-align: justify;
      text-align-last: left;
    }
    .card__heading--sub {
      color: white!important;
      opacity: .5!important;
    }
  }

  &__head {
    margin: 1rem 1rem 0;

    a.card__heading::after{
      position: absolute;
      content: "";
      height: .2rem;
      opacity: 1;
      background-color: #333;
    }

    .card__heading {
      position: relative;
      font-family: Lora, sans-serif;
      font-size: 1.5rem;
      text-decoration: none;
      color: #333;
      font-weight: bold;
      padding: 0;
      margin: 0;

      &--sub {
        font-size: 1.2rem;
        text-transform: uppercase;
        opacity: .8;
      }
    }
  }

  @keyframes slide {
    from {
      right: 100%;
      opacity: 0;
    }
    to {
      right: 0;
      opacity: 1;
    }
  }
  .card__heading--footer {
    font-family: Lora, sans-serif;
    font-size: 1rem;
    opacity: .4;
    color: crimson;
  }

  &__description {
    font-size: 1.2rem;
    font-family: Roboto, sans-serif;
    margin: 1rem;
    padding: 0;
    font-weight: 400;
  }
  &__tags {
    margin: .7rem 1rem 0;
  }
}

.card:hover a.card__heading::after {
  bottom: 0;
  left: 0;
  right: 0;
  animation-name: slide;
  animation-duration: 1s;
  background-color: #333;
}

.card__footer {
    margin: 1rem;
    justify-self: flex-end!important;
    border: thin solid red;
    align-self: flex-end!important;
  }

.btn {
  padding: .7rem 2rem;
  margin: .5rem 0;
  border: .2rem solid $bg;
  background-color: $bg;
  color: crimson;
  font-weight: 700;
  border-radius: .3rem;
  text-decoration: none;
  text-transform: uppercase;
  font-family: Roboto, sans-serif;
  transition: .3s ease-in-out;
  cursor: pointer;
  transform: translate(0);
  
  display: inline-flex;
  justify-content: center;
  align-items: center;

  &--outline {
    background-color: transparent;
    border-color: $bg;
    color: $bg;
  }

  .btn__icon {
    font-size: 2rem;
    margin: 0 1rem 0 0;
  }

  &:hover {
    transform: translateY(-3px);
    box-shadow: 0 3px 5px 0px rgba($color: black, $alpha: .5);
  }

  &:active {
    transform: translateY(3px);
    box-shadow: none;
  }

}

@keyframes shake {
  from {
    transform: translateX(-3px);
  }
  to {
    transform: translateX(3px);
  }
}

@media (min-width: 1200px) {
  .section {
    padding: 1rem 4rem;
  }
  .slider {
    justify-content: space-between;
  }
  .container--des-flex {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

    padding: 3rem 0;
  }
  .card  {
    min-width: calc(100% / 3.2);
    max-width: calc(100% / 3.2);

    &--experience{ 
      min-width: calc(100% / 3.5);
      max-width: calc(100% / 3.5);
    }
  }

  .heading {
    font-variant: small-caps;

    &--small {
      font-size: 2rem;
    }

  }
}
</style>
