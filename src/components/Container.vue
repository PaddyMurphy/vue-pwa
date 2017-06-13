<template>
  <div class="layout">

    <header-layout />

    <section class="section content section--about" id="about">
      <div class="container">
        <h2 class="title is-spaced">About</h2>
        <p>UX/UI Developer with over 10 years experience creating web applications. I enjoy working collaboratively with a team to design, prototype, test and deliver products.</p>
      </div>
    </section>

    <section class="section content section--casestudy" id="case-study">
      <div class="container">
        <h2 class="title is-spaced">Case Study</h2>
        <h3 class="subtitle">HomeAway Onboarding</h3>
        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

        <!-- TODO: insert image gallery -->

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>

        <!-- TODO: insert image gallery -->

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div> <!-- END container -->
    </section>

    <lazy-background
      class="section section--photo"
      image-source="static/img/layout/devils-river.jpg"
      loadingImage="static/img/layout/blank.png"
      errorImage="static/img/layout/blank.png">
    </lazy-background>

    <div class="photo-window">
      <span class="photo-title">Devils River, Texas</span>
    </div>

    <section class="section content section--experience" id="experience">
      <div class="container">
        <h2 class="title is-spaced">Experience</h2>
        <h3 class="subtitle">UX Developer at HomeAway <small>(2011 - 2016)</small></h3>
        <p>
            desc..
        </p>

        <h3 class="subtitle">Front-end Developer at BancVue <small>(2009 - 2011)</small></h3>
        <ul>
          <li>Create credit union web sites using html, css, Javascript and a content management system.</li>
          <li>Introduced the use of SASS, css3 and methods to ensure cross browser consistency.</li>
          <li>Improved the efficiency, quality and speed of sites created.</li>
        </ul>

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.</p>
      </div>
    </section>

    <contact-layout />

    <footer-layout />
  </div>
</template>

<script>
import ContactLayout from '@/components/ContactLayout';
import HeaderLayout from '@/components/HeaderLayout';
import FooterLayout from '@/components/FooterLayout';
import LazyBackgroundImages from '@/components/VueLazyBackgroundImage';
import scrollBreakpoint from 'scroll-breakpoint'; // eslint-disable-line
import Smoothscroll from 'smooth-scroll';
// import Wallop from 'wallop';

export default {
  name: 'layout',

  mounted: function () {
    // animate scrollto
    Smoothscroll.init({
      'easing': 'easeOutQuad',
      'offset': 40
    });

    // show / hide the top nav
    window.scrollBreakpoint(function () {
      return this.scrollY > 100;
    }, function (isTrue) {
      document.body.classList[isTrue ? 'add' : 'remove']('sticky-header');
    });
  },

  components: {
    'lazy-background': LazyBackgroundImages,
    'header-layout': HeaderLayout,
    'contact-layout': ContactLayout,
    'footer-layout': FooterLayout
  }
}
</script>

<style lang="sass">
// import initial variables
@import '../../node_modules/bulma/sass/utilities/initial-variables'
// // import custom variables
@import '../assets/sass/bulma-styles.sass'
// Import the rest of Bulma
@import '../../node_modules/bulma/bulma'

.photo-title
  text-shadow: 0 0 4px rgba(0, 0, 0, 0.3)
  bottom: 1.5em
  color: #fff
  font-size: 0.9em
  font-weight: bold
  position: absolute
  right: 3em
  z-index: 1

.photo-window
  height: 20em
  position: relative
  .photo-title
    opacity: 0.8

.section
  padding: 3em 4em

  .container
    margin-left: auto
    margin-right: auto
    max-width: $tablet

  &.content
    margin-bottom: 0

  &--about
    background: $white

  &--casestudy
    background: $color-section

  &--photo
    background-position: top center
    background-repeat: no-repeat
    background-size: cover
    padding: 0
    height: 100vh
    width: 100vw
    position: fixed
    bottom: 0
    left: 0
    z-index: -1

  &--experience
    background: $color-section

.copyright
  margin: 0 0 0 2em

.contact-photo
  width: 100%
  max-width: 150px
  height: auto

</style>
