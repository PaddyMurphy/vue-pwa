<template>
  <div id="app">
    <main>
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
export default {
  name: 'app'
}
</script>

<style lang="sass">
  // import initial variables
  @import '../node_modules/bulma/sass/utilities/initial-variables'
  // import custom variables
  @import 'assets/sass/bulma-styles.sass'
  // Import the rest of Bulma
  @import '../node_modules/bulma/bulma'
</style>
