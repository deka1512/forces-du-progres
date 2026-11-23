<script setup lang="ts">
withDefaults(defineProps<{title:string;description:string;eyebrow?:string;image?:string}>(),{image:''})
</script>
<template>
  <section class="page-hero" :class="{ 'has-image': !!image }" :style="image ? { backgroundImage: `url('${image}')` } : undefined">
    <div class="hero-orb"/>
    <UContainer class="hero-content">
      <div class="eyebrow light"><span/>{{eyebrow||'FORCE DU PROGRÈS · RDC'}}</div>
      <h1>{{title}}</h1>
      <p>{{description}}</p>
    </UContainer>
  </section>
</template>