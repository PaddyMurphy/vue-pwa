<template>
  <div class="layout">

    <header-layout />

    <div class="hero is-primary" style="background-image: url('static/img/layout/bugaboo-spire.jpg')">
      <div class="hero-body">
        <h1 class="title is-1">Patrick Lewis</h1>
        <h2 class="subtitle is-4">User Experience Developer</h2>
        <span class="photo-title">Bugaboo Spire, Canada</span>
      </div>
    </div>

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

    <section class="section content section--contact" id="contact">
      <div class="container">
        <div class="contact-content">
          <h2 class="title is-spaced">Contact</h2>
          <p>
            Email me at <span style="unicode-bidi:bidi-override; direction: rtl;"> moc.liamg@siwelbkcirtap</span>
          </p>
          <ul class="contact-list">
            <li><a href="https://www.linkedin.com/in/patrick-lewis-4b71484/">LinkedIn</a></li>
            <li><a href="https://www.flickr.com/photos/paddymurphy">Flickr</a></li>
            <li><a href="https://dribbble.com/paddymurphy">Dribbble</a></li>
            <li><a href="https://vimeo.com/paddymurphy">Vimeo</a></li>
          </ul>
        </div>
        <div class="contact-side">
          <img class="b-lazy contact-photo"
            src='data:image/gif;base64,R0lGODlhAQABAAAAACH5BAEKAAEALAAAAAABAAEAAAICTAEAOw=='
            width="150" height="195"
            data-src="static/img/layout/patrick.jpg"
            alt="drawing of Patrick"
          />
        </div>
      </div><!-- END .container -->
    </section>

    <footer-layout />
  </div>
</template>

<script>
import HeaderLayout from '@/components/HeaderLayout';
import FooterLayout from '@/components/FooterLayout';
import LazyBackgroundImages from '@/components/VueLazyBackgroundImage';
import scrollBreakpoint from 'scroll-breakpoint'; // eslint-disable-line
// import Smoothscroll from 'smooth-scroll';
// import Blazy from 'bLazy';
// import Wallop from 'wallop';

export default {
  name: 'layout',

  mounted: function () {
    // show / hide the top nav
    window.scrollBreakpoint(function () {
      return this.scrollY > 100;
    }, function (isTrue) {
      // This code will be executed exactly once when you'll reach the breakpoint.
      document.body.classList[isTrue ? 'add' : 'remove']('sticky-header');
    });
  },

  components: {
    'lazy-background': LazyBackgroundImages,
    'header-layout': HeaderLayout,
    'footer-layout': FooterLayout
  }
}
</script>

<style lang="sass" scoped>
// import initial variables
@import '../../node_modules/bulma/sass/utilities/initial-variables'
// // import custom variables
@import '../assets/sass/bulma-styles.sass'
// Import the rest of Bulma
@import '../../node_modules/bulma/bulma'

.hero
  color: #fff
  text-align: center
  height: 80vh
  // background-image set in template
  background-position: top center
  background-repeat: no-repeat
  background-size: cover
  position: relative
  width: 100vw
  &.is-primary
    background-blend-mode: hard-light
    background-color: rgba(0,0,0,0.25)

.hero-body
  padding-top: 24vh

.title
  font-weight: $weight-semibold

.hero-body .title,
.hero-body .subtitle
  opacity: 1
  position: relative
  transition: all 0.3s
  z-index: 1
  .sticky-header &
    opacity: 0
    transform: translateY(-1em)


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

  .container:not(:last-child)
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

  &--contact
    background: $white
    display: flex
    position: relative


</style>
