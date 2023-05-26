<template>
  <header>
    <div>
      <nav-app />
    </div>
  </header>

  <RouterView />
  <footer-app />
</template>

<script>
import NavApp from './components/NavApp.vue'
import FooterApp from './components/FooterApp.vue'

export default {
  components: { NavApp, FooterApp },
  name: 'App'
}
</script>
