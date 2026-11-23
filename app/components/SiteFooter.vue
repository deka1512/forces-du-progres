<script setup lang="ts">
const year=new Date().getFullYear()
const links=[{label:'Accueil',to:'/'},{label:'Présidence nationale',to:'/presidence'},{label:'Organisation',to:'/organisation'},{label:'Actualités',to:'/actualites'},{label:'Activités & médias',to:'/activites'},{label:'Contact',to:'/contact'}]
</script>
<template>
  <footer class="site-footer">
    <UContainer>
      <div class="footer-main">
        <div>
          <NuxtLink to="/" class="brand brand-light"><span class="brand-logo-slot">LOGO</span><span class="brand-copy"><strong>FORCE DU PROGRÈS</strong><small>PORTAIL NATIONAL · RDC</small></span></NuxtLink>
          <p class="footer-brand-note">Portail institutionnel de présentation et d’information de la Force du Progrès en République démocratique du Congo.</p>
        </div>
        <nav class="footer-links" aria-label="Navigation de pied de page">
          <h3>Explorer le portail</h3>
          <NuxtLink v-for="item in links" :key="item.to" :to="item.to">{{item.label}}</NuxtLink>
        </nav>
        <div class="footer-links">
          <h3>Information & contact</h3>
          <p class="footer-contact-note">Pour toute demande institutionnelle, médiatique ou organisationnelle, consultez l’espace de contact du portail.</p>
          <UButton to="/contact" color="neutral" class="text-white" variant="outline">Accéder au contact <UIcon name="i-lucide-arrow-up-right"/></UButton>
        </div>
      </div>
      <div class="footer-bottom">
        <span>© {{year}} Force du Progrès. Tous droits réservés.</span>
        <a href="https://bydeka.net" target="_blank" rel="noopener noreferrer">Proudly made by Bydeka</a>
      </div>
    </UContainer>
  </footer>
</template>