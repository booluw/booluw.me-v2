<template>
  <div id="app">
    <app-header />
    <router-view/>
  </div>
</template>

<script>
import AppHeader from '@/components/AppHeader.vue'

export default {
  name: 'App',
  components: {
    'app-header': AppHeader
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
  background-color: $grey;
}

.slider {
  display: flex;
  overflow-x: auto;
  margin: 1rem 0 .5rem 0;
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

  &--small {
    font-variant: normal;
    text-transform: uppercase;
    font-size: 1.3rem;
    text-shadow: 0px 0px 2px black;
    letter-spacing: .2rem;
  }

}

.chip {
  padding: .25rem .5rem;
  margin: .2rem;
  -webkit-margin-top-collapse: collapse;
  background-color: aliceblue;
  border-radius: 1rem;
  font-weight: 600;
}

.card {
  position: relative;
  min-width: calc(100% / 1.1);

  background-color: $bg;
  border-top: .3rem solid crimson;
  border-radius: .5rem;
  padding: 0 0 1rem;
  margin: 0 .3rem;
  box-shadow: 5px 5px 10px rgba($color: $base, $alpha: .5);

  &--with-img {
    .card__img {
      width: 100%;
      height: auto;
    }
  }

  &--experience {
    width: auto;
    border-top: none;
    border-left: .5rem solid crimson;
    margin: .7rem 1.8rem .7rem 1rem;
    padding: 2rem 0;

    .card__icon {
      position: absolute;
      left: -1.8rem;
      top: .7rem;
      
      background-color: crimson;
      color: $bg;
      padding: .8rem 1rem;
      border-radius: 50%;
      font-size: 1.5rem;
    }

    .card__description {
      margin: 1rem 0 0;
    }
  }

  &__head {
    margin: 1rem 1rem 0;

    .card__heading {
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
  }

  &__footer {
    margin: 1rem;
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
