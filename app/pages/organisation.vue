<script setup lang="ts">import { provinces } from '~/data/site';useSeoMeta({title:'Organisation | Force du Progrès'})</script>
<template>
  <div>
    <PageHero title="Organisation nationale" description="Une organisation structurée autour de la coordination nationale et de relais territoriaux à travers la République démocratique du Congo."/>
    <section class="content-section">
      <UContainer>
        <div class="section-heading"><div><div class="section-eyebrow">STRUCTURE ORGANISATIONNELLE</div><h2>Une coordination à plusieurs niveaux</h2><p>Une architecture qui rapproche les orientations nationales des réalités locales.</p></div></div>
        <div class="org-chart">
          <div class="org-node primary-node"><UIcon name="i-lucide-landmark"/><b>Présidence nationale</b><small>Joel Mpaba Mukiri · alias Moselu</small></div>
          <div class="org-line"/>
          <div class="org-node"><UIcon name="i-lucide-network"/><b>Coordination nationale</b><small>Orientation et coordination générale</small></div>
          <div class="org-line"/>
          <div class="org-levels">
            <div class="org-node"><UIcon name="i-lucide-map"/><b>Coordinations provinciales</b><small>Relais dans les provinces</small></div>
            <div class="org-node"><UIcon name="i-lucide-building"/><b>Coordinations urbaines</b><small>Villes et communes</small></div>
            <div class="org-node"><UIcon name="i-lucide-map-pinned"/><b>Coordinations territoriales</b><small>Territoires et secteurs</small></div>
            <div class="org-node"><UIcon name="i-lucide-users"/><b>Sections locales</b><small>Proximité et participation</small></div>
          </div>
        </div>
        <div class="province-heading"><h2>Les 26 provinces de la RDC</h2><UBadge color="primary" variant="subtle">Couverture nationale</UBadge></div>
        <div class="province-grid"><div v-for="(province,index) in provinces" :key="province" class="province-item"><span>{{String(index+1).padStart(2,'0')}}</span>{{province}}</div></div>
        <div class="three-grid">
          <UCard><UIcon name="i-lucide-network"/><h3>Coordination</h3><p>Relier les différents niveaux d’organisation et faciliter la circulation de l’information.</p></UCard>
          <UCard><UIcon name="i-lucide-map-pin"/><h3>Proximité</h3><p>Faire connaître les réalités des provinces, villes, communes et territoires.</p></UCard>
          <UCard><UIcon name="i-lucide-users"/><h3>Participation</h3><p>Encourager l’implication et le dialogue au sein des communautés.</p></UCard>
        </div>
      </UContainer>
    </section>
  </div>
</template>