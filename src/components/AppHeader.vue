<template>
  <header class="header">
    <div class="header__logo">booluw</div>
    <nav class="header__nav">
      <ul class="nav__list">
        <li class="nav__list-item">
          <a href="#projects" class="nav__link">Projects</a>
        </li>
        <li class="nav__list-item">
          <a href="//medium.com/@booluw" to="/" class="nav__link">Articles</a>
        </li>
        <li class="nav__list-item">
          <a href="mailto:jaycewap@gmail.com" title="Send me an email" class="btn">
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
  background-color: $base;
  color: $base;
  border-top: .2rem solid $base;
  border-bottom: .05rem solid $color;

  &__logo {
    font-weight: bold;
    font-family: Lora, serif;
    position: relative;
    color: $color;
    margin: 0 0 1rem;
    
    &::after {
      position: absolute;
      content: '';
      height: .2rem;
      width: 30%;
      background-color: $secondary;
      bottom: -.2rem;
      left: .7rem;
      border-radius: 1rem;
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
  padding: .5rem 1rem;
  text-decoration: none;
  color: $secondary;
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

    &__logo {
      font-size: 2rem;
    }
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