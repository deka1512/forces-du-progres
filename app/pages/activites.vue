<script setup lang="ts">import { activityFormats } from '~/data/site';useSeoMeta({title:'Activités & médias | Force du Progrès'})</script>
<template>
  <div>
    <PageHero title="Activités & médias" description="Les espaces d’échange, de formation, de solidarité et de participation qui peuvent faire vivre l’engagement communautaire."/>
    <section class="content-section">
      <UContainer>
        <div class="section-heading"><div><div class="section-eyebrow">INITIATIVES ET ENGAGEMENT</div><h2>Des actions au plus près des communautés</h2><p>Des formats d’activités pour favoriser le dialogue, la participation et la cohésion sociale.</p></div></div>
        <div class="activity-grid">
          <UCard v-for="item in activityFormats" :key="item.title" class="activity-card" :ui="{body:'p-0 sm:p-0'}">
            <img :src="item.image" :alt="'Illustration : '+item.title"/>
            <div class="activity-body"><UBadge>{{item.type}}</UBadge><h3>{{item.title}}</h3><p>{{item.description}}</p></div>
          </UCard>
        </div>
        <div class="media-placeholder"><UIcon name="i-lucide-images"/><div><h3>Galerie photos et vidéos</h3><p>Un espace pour retrouver les reportages, les prises de parole et les archives multimédias du mouvement.</p></div><UBadge color="primary">Médias</UBadge></div>
      </UContainer>
    </section>
  </div>
</template>