<script setup lang="ts">
import { newsItems } from '~/data/site'
const filters=['Toutes',...new Set(newsItems.map(item=>item.category))]
const active=ref('Toutes')
const filtered=computed(()=>active.value==='Toutes'?newsItems:newsItems.filter(item=>item.category===active.value))
useSeoMeta({title:'Actualités & engagements | Force du Progrès'})
</script>
<template>
  <div>
    <PageHero title="Actualités & engagements" description="Les grandes thématiques, les prises de parole et les informations qui rythment la vie du mouvement."/>
    <section class="content-section">
      <UContainer>
        <div class="section-heading"><div><div class="section-eyebrow">INFORMATIONS ET THÉMATIQUES</div><h2>Les sujets au cœur de notre engagement</h2><p>Des contenus consacrés à la citoyenneté, à la jeunesse, à la solidarité et au développement.</p></div></div>
        <div class="filter-row"><UButton v-for="f in filters" :key="f" :color="active===f?'primary':'neutral'" :variant="active===f?'solid':'outline'" @click="active=f">{{f}}</UButton></div>
        <div class="news-grid">
          <UCard v-for="item in filtered" :key="item.title" class="news-card" :ui="{body:'p-0 sm:p-0'}">
            <img class="news-image" :src="item.image" :alt="'Illustration : '+item.title"/>
            <div class="news-body"><UBadge>{{item.category}}</UBadge><h3>{{item.title}}</h3><p>{{item.excerpt}}</p></div>
          </UCard>
        </div>
      </UContainer>
    </section>
  </div>
</template>