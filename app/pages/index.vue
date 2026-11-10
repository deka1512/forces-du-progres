<script setup lang="ts">
import { newsItems } from '~/data/site'
useSeoMeta({ title: 'Accueil | Force du Progrès' })
const priorities = [
  { icon: 'i-lucide-users', title: 'Engagement citoyen', text: 'Placer l’écoute, la participation et la responsabilité au centre de la vie collective.' },
  { icon: 'i-lucide-graduation-cap', title: 'Jeunesse et avenir', text: 'Encourager la formation, l’initiative et le leadership responsable des jeunes.' },
  { icon: 'i-lucide-hand-heart', title: 'Solidarité nationale', text: 'Renforcer l’entraide, la cohésion sociale et le respect entre les communautés.' },
  { icon: 'i-lucide-landmark', title: 'Institutions et dialogue', text: 'Privilégier le dialogue, la paix et la participation dans le respect du cadre légal.' }
]
</script>
<template>
  <div>
    <section class="home-hero">
      <div class="home-image"/><div class="home-shade"/>
      <UContainer class="home-content">
        <div class="eyebrow light"><span/>PORTAIL NATIONAL · RDC</div>
        <h1>FORCE DU<br/><em>PROGRÈS</em></h1>
        <p>Un espace de présentation et d’information consacré à l’engagement citoyen, à la solidarité et à la participation communautaire en République démocratique du Congo.</p>
        <div class="hero-actions">
          <UButton to="/organisation" size="xl">Découvrir l’organisation</UButton>
          <UButton to="/actualites" size="xl" color="neutral" class="text-white" variant="outline">Nos engagements</UButton>
        </div>
        <div class="hero-caption">RÉPUBLIQUE DÉMOCRATIQUE DU CONGO</div>
      </UContainer>
    </section>
    <section class="intro-strip">
      <UContainer class="intro-grid">
        <div><div class="section-eyebrow">UNE AMBITION COLLECTIVE</div><h2>Agir ensemble.<br/><span>Faire progresser la société.</span></h2></div>
        <p>La Force du Progrès est présentée ici à travers les valeurs de responsabilité, de solidarité, de dialogue et de participation citoyenne. Ce portail permet de découvrir les repères du mouvement, ses thématiques d’engagement et ses espaces de communication.</p>
      </UContainer>
    </section>
    <section class="content-section">
      <UContainer>
        <div class="section-heading"><div><div class="section-eyebrow">NOS AXES D’ENGAGEMENT</div><h2>Des priorités tournées vers la communauté</h2><p>Des thèmes qui mettent en avant la participation et le progrès collectif.</p></div></div>
        <div class="three-grid">
          <UCard v-for="item in priorities" :key="item.title"><UIcon :name="item.icon"/><h3>{{item.title}}</h3><p>{{item.text}}</p></UCard>
        </div>
      </UContainer>
    </section>
    <section class="president-band">
      <UContainer class="president-inner">
        <UIcon name="i-lucide-landmark" class="president-icon"/>
        <div><div class="section-eyebrow light">PRÉSIDENCE NATIONALE</div><h2>Joel Mpaba Mukiri <span>« Moselu »</span></h2><p>Une direction nationale au service de la coordination et de la représentation du mouvement.</p></div>
        <UButton to="/presidence" color="neutral" class="text-white" variant="outline">Découvrir la présidence</UButton>
      </UContainer>
    </section>
    <section class="content-section soft">
      <UContainer>
        <div class="section-heading"><div><div class="section-eyebrow">THÉMATIQUES ET INFORMATIONS</div><h2>Les sujets qui nous rassemblent</h2><p>Citoyenneté, jeunesse, cohésion sociale, gouvernance et développement local.</p></div><NuxtLink to="/actualites" class="text-link">Toutes les thématiques <UIcon name="i-lucide-arrow-up-right"/></NuxtLink></div>
        <div class="news-grid">
          <UCard v-for="item in newsItems.slice(0,3)" :key="item.title" class="news-card" :ui="{body:'p-0 sm:p-0'}">
            <img class="news-image" :src="item.image" :alt="'Illustration : '+item.title"/>
            <div class="news-body"><UBadge>{{item.category}}</UBadge><h3>{{item.title}}</h3><p>{{item.excerpt}}</p></div>
          </UCard>
        </div>
      </UContainer>
    </section>
    <section class="content-section">
      <UContainer>
        <div class="section-heading"><div><div class="section-eyebrow">ANCRAGE NATIONAL</div><h2>Un pays, 26 provinces, une diversité de réalités</h2><p>Un portail pour relier les informations nationales et les repères territoriaux.</p></div></div>
        <div class="stat-grid">
          <UCard><strong>26</strong><b>Provinces</b><small>La diversité territoriale de la RDC</small></UCard>
          <UCard><strong>01</strong><b>Cadre national</b><small>Un espace commun de présentation</small></UCard>
          <UCard><strong>06</strong><b>Rubriques principales</b><small>Une navigation claire et accessible</small></UCard>
        </div>
        <div class="center-action"><UButton to="/organisation">Explorer l’organisation</UButton></div>
      </UContainer>
    </section>
  </div>
</template>