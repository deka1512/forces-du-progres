<script setup lang="ts">
const year=new Date().getFullYear()
const links=[{label:'Présidence nationale',to:'/presidence'},{label:'Organisation',to:'/organisation'},{label:'Actualités',to:'/actualites'},{label:'Activités & médias',to:'/activites'},{label:'Contact',to:'/contact'}]
</script>
<template>
  <footer class="site-footer">
    <UContainer>
      <div class="footer-main">
        <div>
          <NuxtLink to="/" class="brand brand-light"><span class="brand-mark">FP</span><span class="brand-copy"><strong>FORCE DU PROGRÈS</strong><small>PORTAIL NATIONAL · RDC</small></span></NuxtLink>
          <p>Un espace de présentation, d’information et de valorisation de l’engagement citoyen, de la solidarité et de la participation communautaire.</p>
        </div>
        <div class="footer-links">
          <h3>Navigation</h3>
          <NuxtLink v-for="item in links" :key="item.to" :to="item.to">{{item.label}}</NuxtLink>
        </div>
        <div class="footer-links">
          <h3>Restons en contact</h3>
          <p>Retrouvez les informations institutionnelles et les canaux de communication publiés par la coordination.</p>
          <UButton to="/contact" color="neutral" class="text-white" variant="outline">Accéder au contact</UButton>
        </div>
      </div>
      <div class="footer-bottom">
        <span>© {{year}} Force du Progrès. Tous droits réservés.</span>
        <a href="https://bydeka.net" target="_blank" rel="noopener noreferrer">Proudly made by Bydeka</a>
      </div>
    </UContainer>
  </footer>
</template>