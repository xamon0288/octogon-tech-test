<template>
  <nav class="navbar" :class="{ 'navbar-hidden': isNavbarHidden }">
    <div class="navbar-item hamburger-container" @click="toggleMobileNav">
      <div class="hamburger"></div>
    </div>
    <div class="nav-container">
      <div class="navbar-left">
        <div class="navbar-item">
          <a href="#accueil" class="navbar-link">OCTOGON TECHNOLOGY</a>
        </div>
      </div>
      <div class="navbar-middle">
        <div class="navbar-item">
          <a href="#accueil" class="navbar-link" @click="scrollToSection('#accueil')">ACCUEIL</a>
        </div>
        <div class="navbar-item">
          <a href="#blockchain" class="navbar-link" @click="scrollToSection('#blockchain')"
            >BLOCKCHAIN</a
          >
        </div>
        <div class="navbar-item">
          <a href="#ai" class="navbar-link" @click="scrollToSection('#ai')">I.A</a>
        </div>
        <div class="navbar-item">
          <a href="#is" class="navbar-link" @click="scrollToSection('#is')">INGENIERIE SPACIAL</a>
        </div>
      </div>
      <div class="navbar-right">
        <div class="navbar-item">
          <a href="#contact" class="navbar-link" @click="scrollToSection('#contact')">CONTACT</a>
        </div>
      </div>
    </div>
    <div class="mobile-nav" v-if="isMobileNavVisible">
      <div class="mobile-nav-content">
        <div class="navbar-item close" @click="closeMobileNav">
          <p>X</p>
        </div>
        <div class="navbar-item">
          <p class="mobile-nav-link nav-logo">OCTOGON TECHNOLOGY</p>
        </div>
        <div class="navbar-item" @click="closeMobileNav">
          <a href="#accueil" class="mobile-nav-link">ACCUEIL</a>
        </div>
        <div class="navbar-item" @click="closeMobileNav">
          <a href="#blockchain" class="mobile-nav-link">BLOCKCHAIN</a>
        </div>
        <div class="navbar-item" @click="closeMobileNav">
          <a href="#ai" class="mobile-nav-link">I.A</a>
        </div>
        <div class="navbar-item" @click="closeMobileNav">
          <a href="#is" class="mobile-nav-link">INGENIERIE SPATIAL</a>
        </div>
        <div class="navbar-item" @click="closeMobileNav">
          <a href="#contact" class="mobile-nav-link">CONTACT</a>
        </div>
      </div>
    </div>
  </nav>
</template>

<script>
export default {
  name: 'NavApp',
  data() {
    return {
      isNavbarHidden: false,
      isMobileNavVisible: false,
      isMegaMenuVisible: false,
      isLoginModalVisible: false
    }
  },
  mounted() {
    window.addEventListener('scroll', this.handleScroll)
  },
  beforeUnmount() {
    window.removeEventListener('scroll', this.handleScroll)
  },
  methods: {
    handleScroll() {
      const currentScroll = window.pageYOffset || document.documentElement.scrollTop
      this.isNavbarHidden = currentScroll > this.prevScroll
      this.prevScroll = currentScroll
      const navbar = document.querySelector('.navbar')
      if (navbar) {
        if (currentScroll > 0) {
          navbar.classList.add('navbar-scrolled')
        } else {
          navbar.classList.remove('navbar-scrolled')
        }
      }
    },
    toggleMobileNav() {
      this.isMobileNavVisible = !this.isMobileNavVisible
    },
    closeMobileNav() {
      this.isMobileNavVisible = false
    },
    scrollToSection(sectionId) {
      const section = document.querySelector(sectionId)
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' })
        this.closeMobileNav() // Close the mobile menu after clicking a navigation item
      }
    }
  }
}
</script>

<style scoped></style>
