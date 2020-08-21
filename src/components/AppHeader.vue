<template>
  <header class="header">
    <div class="header__logo">booluw</div>
    <nav class="header__nav">
      <ul class="nav__list">
        <li class="nav__list-item">
          <router-link to="/" class="nav__link">Project</router-link>
        </li>
        <li class="nav__list-item">
          <router-link to="/" class="nav__link">Blog</router-link>
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
  justify-content: space-between;
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

  &-item {
    list-style-type: none;
  }
}
.nav__link {
  padding: .5rem 1rem;
  text-decoration: none;
  color: $secondary;
}

@media (min-width: 1200px) {
  .header {
    padding: 1rem 4rem;

    &__logo {
      font-size: 2rem;
    }
  }

  .nav__link {
    font-size: 1.3rem;
  }
}
</style>