<template>
  <main>
    <div class="hero-container">
      <div class="hero-wrap" id="accueil">
        <div class="hero flex">
          <div class="title hero-flex">
            <h1>
              <span class="hero-company">OCT<span class="logo-color">O</span>GON TECHNOLOGY</span>
              <div class="highlight hero-cat" :class="{ 'slide-in': isTransitionActive }">
                {{ currentString }}
              </div>
            </h1>
          </div>
          <!-- <div class="title-right reveal">
              <img src="/octogon_technology.png" alt="Octogon Technology Logo" class="hero-logo" />
            </div> -->
          <a href="#intro" class="btn hero-btn">Découvrir l'entreprise</a>
        </div>
      </div>
    </div>

    <!-- Intro -->
    <section id="intro" class="intro container">
      <h3>Ensemble, construisons l'avenir technologique de demain.</h3>
      <p>
        Explorez le monde de l'innovation avec Octogon Technology, votre partenaire de confiance en
        matière de blockchain, d'intelligence artificielle et d'ingénierie spatiale.
      </p>
    </section>

    <!-- Details Sections -->
    <section class="details-container">
      <div class="details-path">
        <!-- BLOCKCHAIN -->
        <div class="blockchain container details-spacer" id="blockchain">
          <div class="block-text">
            <div class="block-title">
              <p class="block-sub">
                Sécurité<span class="dot"> . </span>Confiance<span class="dot"> . </span
                >Transparence
              </p>
              <h4>Blockchain</h4>
              <p class="block-desc">
                Chez Octogon Technology, nous offrons une expertise complète en matière de
                blockchain. Nous concevons et développons des solutions personnalisées basées sur
                cette technologie révolutionnaire, permettant la création de contrats intelligents
                sécurisés, la gestion transparente des transactions et la traçabilité des données.
                Avec notre savoir-faire, préparez-vous à transformer votre entreprise grâce à la
                puissance de la blockchain.
              </p>
            </div>
          </div>
          <div class="block-card">
            <div class="card"><p>Sécurité renforcée avec la blockchain</p></div>
            <div class="card"><p>Traçabilité transparente des transactions</p></div>
            <div class="card"><p class="center">Gestion décentralisée des données</p></div>
          </div>
        </div>

        <!-- Intelligence Artificielle -->
        <div class="ai container details-spacer" id="ai">
          <div class="block-text">
            <div class="block-title">
              <p class="block-sub">
                Automatisation<span class="dot"> . </span>Analyse<span class="dot"> . </span
                >Performance
              </p>
              <h4>Intelligence Artificielle</h4>
              <p class="block-desc">
                Chez Octogon Technology, nous proposons une gamme complète de services en
                intelligence artificielle. De la conception d'algorithmes sophistiqués à
                l'implémentation de systèmes d'apprentissage automatique avancés, nous exploitons le
                pouvoir de l'IA pour améliorer l'efficacité opérationnelle, automatiser les
                processus, analyser les données complexes et créer des expériences utilisateur
                intelligentes. Donnez à votre entreprise un avantage concurrentiel grâce à notre
                expertise en IA.
              </p>
              <div class="block-card hidden">
                <div class="card center"><p class="center">Performance accrue grâce à l'IA</p></div>
                <div class="card"><p>Automatisation intelligente des processus</p></div>
                <div class="card">
                  <p>Expériences utilisateur personnalisées et intelligentes</p>
                </div>
              </div>
            </div>
          </div>
        </div>

        <!-- Ingeneirie Spatiale -->
        <div class="is container details-spacer" id="is">
          <div class="block-text">
            <div class="block-title">
              <p class="block-sub">
                Conception<span class="dot"> . </span>Solutions<span class="dot"> . </span>Expertise
              </p>
              <h4>Ingénierie Spatiale</h4>
              <p class="block-desc">
                Chez Octogon Technology, nous offrons une expertise spécialisée en ingénierie
                spatiale. Nous concevons et développons des solutions innovantes pour l'exploration
                spatiale, la conception de véhicules spatiaux, la navigation précise et la
                propulsion avancée. Avec notre savoir-faire, préparez-vous à repousser les
                frontières de l'exploration spatiale et à concrétiser vos projets les plus
                ambitieux.
              </p>
            </div>
          </div>
          <div class="block-card hidden">
            <div class="card"><p>Conception de véhicules spatiaux innovants</p></div>
            <div class="card"><p>Solutions d'ingénierie spatiale personnalisées</p></div>
            <div class="card center"><p class="center">Expertise en propulsion spatiale</p></div>
          </div>
        </div>
      </div>
    </section>
    <!-- CTA -->
    <section id="contact">
      <div class="container">
        <div class="cta">
          <h3>Plate-forme de confiance</h3>
          <p>
            Découvrez les possibilités infinies avec Octogon Technology. Contactez-nous dès
            maintenant pour transformer votre entreprise avec la puissance de la technologie.
            Ensemble, créons un avenir technologique révolutionnaire. Cliquez ici pour commencer
            votre voyage vers l'excellence.
          </p>
          <button class="btn cta-btn">Contactez Nous</button>
        </div>
      </div>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      strings: ['BLOCKCHAIN', 'INTELLIGENCE ARTIFICIELLE', 'INGENIERIE SPACIALE'], // Array of strings
      currentIndex: 1, // Current index of the array
      currentString: 'BLOCKCHAIN', // String to be rendered
      isTransitionActive: true
    }
  },
  mounted() {
    // Start the interval when the component is mounted
    this.startInterval()
  },
  methods: {
    startInterval() {
      setInterval(() => {
        this.isTransitionActive = true // Activate the transition
        this.currentString = this.strings[this.currentIndex]
        this.currentIndex = (this.currentIndex + 1) % this.strings.length
        setTimeout(() => {
          this.isTransitionActive = false // Deactivate the transition after 300ms
        }, 300)
      }, 2000)
    }
  }
}
</script>
