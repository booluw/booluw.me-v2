<template>
  <header class="header">
    <router-link to="/" class="header__logo">booluw</router-link>
    <nav class="header__nav">
      <ul class="nav__list">
        <li class="nav__list-item">
          <a href="#projects" class="nav__link">Projects</a>
        </li>
        <li class="nav__list-item">
          <a href="//medium.com/@booluw" to="/" class="nav__link">Articles</a>
        </li>
        <li class="nav__list-item">
          <a href="mailto:jaycewap@gmail.com" title="Send me an email" class="btn btn--outline">
            <i class="ion icon ion-md-mail btn__icon"></i>
            Hire Me
          </a>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: 'AppHeader',
}
</script>

<style lang="scss" scoped>
$base: #2e0854;
$secondary: #ffcb05;
$grey: #004e89;
$bg: #bbdef0;
$color: #5eb1bf;

.header {
  display: flex;
  align-items: center;
  justify-content: center;
  flex-wrap: wrap;
  padding: 1rem .5rem;
  background-color: #264658;
  color: #264658;
  border-top: .2rem solid $secondary;
  border-bottom: .05rem solid $color;

  &__logo {
    font-weight: bold;
    font-family: Lora, serif;
    position: relative;
    color: $color;
    margin: 0 0 1rem;
    font-size: 2rem;
    text-decoration: none;
    transition: .3s ease-in-out;
    
    &::after {
      position: absolute;
      content: '';
      height: .2rem;
      width: 30%;
      background-color: $secondary;
      bottom: -.2rem;
      left: 1.2rem;
      border-radius: 1rem;
      transition: .3s ease-in-out;
    }

    &:hover {
      color: $secondary;

      &::after {
        background-color: $color;
      }
    }
  }

  &__nav {
    display: flex;
    padding: 0;
    margin: 0;
  }
}

.nav__list {
  display: flex;
  padding: 0;
  margin: 0;
  align-items: center;

  &-item {
    list-style-type: none;
  }
}
.nav__link {
  padding: .5rem;
  margin: 0 .5rem;
  text-decoration: none;
  color: $secondary;
  position: relative;
  transition: .3s ease;

    &::after {      
      position: absolute;
      content: '';
      height: .2rem;
      width: 30%;
      background-color: $secondary;
      bottom: -.1rem;
      left: 1.2rem;
      opacity: 0;
    }

    &:hover {

      &::after {
        bottom: -.1rem;
        left: 1.2rem;
        animation-name: slide;
        animation-duration: 1s;
        background-color: $secondary;
        opacity: 1;
      }
    }
}
@keyframes slide {
  from {
    left: 0;
    opacity: 0;
  }
  to {
    left: 1.2rem;
    opacity: 1;
  }
}

.btn {
  margin: 0;
  padding: .5rem 1rem;

  .btn__icon {
    display: none;
  }
}

@media (min-width: 1200px) {
  .header {
    padding: 1rem 4rem;
    justify-content: space-between;
    flex-wrap: nowrap;
  }

  .nav__link {
    font-size: 1.3rem;
  }
  
  .btn {
  margin: 0;
  padding: .7rem 2rem;

  .btn__icon {
    display: block;
    margin: 0 .5rem 0 0;
    font-size: 1.3rem;
  }
}
}
</style>