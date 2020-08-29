<template>
  <footer class="footer">
    <div>
      <h2 class="heading">i would really love to join your team.</h2>
      <p class="paragraph">
        My values are centered on Team work, Excellence and <wbr />Service delivery.
        Adding me to your team guarantee a better and cleaner codebase,
        which results in a <wbr> better product for your end-users.  
      </p>
      
      <a href="//docs.google.com/document/d/1QwcjFuw6chztKCYIqZjjGfrNDJVNcfEsEfi9V0eySUM/edit?usp=sharing" target="_blank" rel="noreferral" style="text-decoration: none;" title="My Resume on Google Drive">
        <button class="btn btn--outline">
          <i class="ion icon ion-logo-google btn__icon"></i>
          My Resume
        </button>
      </a>
    </div>
    <div>
      <h2 class="heading heading--faint">technologies i work with.</h2>
      <div class="footer__icons">
        <i class="ion icon ion-logo-html5" title="HTML"></i>
        <i class="ion icon ion-logo-css3" title="CSS"></i>
        <img src="../assets/vue.svg" title="VUE JS"/>
        <i class="ion icon ion-logo-javascript" title="JavaScript"></i>
        <i class="ion icon ion-logo-sass" title="Sass"></i>
      </div>
    </div>
    <div class="footer__copywrite">
      Made with <i class="ion icon ion-md-heart" style="margin: 0 .5rem;"></i> and VueJS; Hosted on Firebase <br />
      booluw.me v2.0
    </div>
  </footer>
</template>

<style lang="scss" scoped>
.footer {
  position: relative;
  background-color: black;
  padding: 2rem .5rem 5rem;
  text-align: center;

  & > div:first-of-type {
    margin: 0 0 2rem 0;
  }

  .heading {
    font-size: 2rem;
    color: #ffcb05;
    
    &--faint {
      opacity: .8;
    }
  }

  &__icons {
    width: 100%;
    margin: 2rem 0 0;
    color: darken(#bbdef0, 50);

    font-size: 2rem;
    display: flex;
    justify-content: space-between;

    img {
      width: 2rem;
      height: 1.5rem;
    }
  }

  .paragraph {
    margin: 2rem 0;
    color: white;
    opacity: .5;
    background-color: black;
    font-family: Roboto, sans-serif;
  }
  &__copywrite {
    position: absolute;
    bottom: 1rem;
    left: 0;
    right: 0;
    color: white;
    opacity: .3;
    text-align: center;

    display: flex;
    justify-content: center;

  }
}

@media (min-width: 1200px) {
  .footer {
    text-align: left;
    padding: 4rem 2rem;

    display: flex;
    flex-wrap: nowrap;
    justify-content: space-between;

    & > div:first-of-type {
      flex-basis: 45%;
    }
    & > div:last-of-type {
      flex-basis: 30%;
    }
  }
}
</style>