<script setup lang="ts">
const route=useRoute()
const open=ref(false)
const links=[{label:'Accueil',to:'/'},{label:'Présidence',to:'/presidence'},{label:'Organisation',to:'/organisation'},{label:'Actualités',to:'/actualites'},{label:'Activités & médias',to:'/activites'},{label:'Contact',to:'/contact'}]
watch(()=>route.fullPath,()=>open.value=false)
</script>
<template>
  <header class="site-header">
    <UContainer class="header-inner">
      <NuxtLink to="/" class="brand" aria-label="Force du Progrès, accueil">
        <span class="brand-mark">FP</span>
        <span class="brand-copy"><strong>FORCE DU PROGRÈS</strong><small>PORTAIL NATIONAL · RDC</small></span>
      </NuxtLink>
      <nav class="desktop-nav" aria-label="Navigation principale">
        <NuxtLink v-for="item in links" :key="item.to" :to="item.to" :class="['nav-link',{active:route.path===item.to}]">{{item.label}}</NuxtLink>
      </nav>
      <UButton to="/contact" class="header-cta">Nous contacter</UButton>
      <UButton class="mobile-toggle" color="neutral" variant="ghost" :icon="open?'i-lucide-x':'i-lucide-menu'" aria-label="Ouvrir le menu" @click="open=!open"/>
    </UContainer>
    <div v-if="open" class="mobile-nav">
      <UContainer>
        <NuxtLink v-for="item in links" :key="item.to" :to="item.to" class="mobile-nav-link">{{item.label}} <UIcon name="i-lucide-chevron-right"/></NuxtLink>
      </UContainer>
    </div>
  </header>
</template>