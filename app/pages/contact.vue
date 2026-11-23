<script setup lang="ts">
const state=reactive({name:'',email:'',subject:'Demande d’information',message:''})
const sent=ref(false)
const subjects=['Demande d’information','Coordination provinciale','Presse et médias','Partenariat','Autre demande']
useSeoMeta({title:'Contact | Force du Progrès'})
</script>
<template>
  <div>
    <PageHero title="Entrer en contact" description="Une question, une demande d’information ou une prise de contact institutionnelle ? Utilisez cet espace pour préparer votre message." eyebrow="ÉCHANGES · PRESSE · RENSEIGNEMENTS" image="https://images.unsplash.com/photo-1497366754035-f200968a6e72?auto=format&fit=crop&w=1200&q=48"/>
    <section class="content-section">
      <UContainer>
        <div class="contact-grid">
          <div>
            <div class="section-eyebrow">CONTACT ET INFORMATION</div>
            <h2 class="contact-title">Le dialogue commence ici.</h2>
            <p class="muted">Cet espace est destiné aux demandes d’information, aux échanges avec les médias et aux prises de contact des coordinations territoriales.</p>
            <div class="contact-detail"><UIcon name="i-lucide-map-pin"/><div><b>Siège de la coordination nationale</b><small>Kinshasa, commune de la Gombe · RDC</small></div></div>
            <div class="contact-detail"><UIcon name="i-lucide-phone"/><div><b>Téléphone & WhatsApp</b><small>+243 000 000 000</small></div></div>
            <div class="contact-detail"><UIcon name="i-lucide-mail"/><div><b>Adresse électronique</b><small>coordination@forcesduprogres.example</small></div></div>
            <div class="contact-detail"><UIcon name="i-lucide-newspaper"/><div><b>Presse et médias</b><small>presse@forcesduprogres.example</small></div></div>
            <div class="contact-detail"><UIcon name="i-lucide-clock"/><div><b>Accueil et renseignements</b><small>Du lundi au vendredi · 08 h 00 – 16 h 00</small></div></div>
            <div class="contact-note"><UIcon name="i-lucide-info"/><span>Coordonnées provisoires de démonstration : le numéro, les adresses e-mail et le lieu précis devront être confirmés par la coordination nationale avant publication officielle.</span></div>
          </div>
          <UCard>
            <div v-if="sent" class="form-success">
              <UIcon name="i-lucide-check-circle"/><h3>Message préparé</h3>
              <p>Votre message est prêt. La transmission en ligne sera disponible lorsque le canal officiel sera connecté.</p>
              <UButton color="neutral" variant="outline" @click="sent=false">Rédiger un autre message</UButton>
            </div>
            <form v-else class="contact-form" @submit.prevent="sent=true">
              <h3>Écrire au portail</h3>
              <p class="muted">Les messages sont préparés dans cette interface. L’envoi réel sera activé après connexion du canal officiel.</p>
              <UFormField label="Nom complet" required><UInput v-model="state.name" placeholder="Votre nom" icon="i-lucide-user" size="xl" class="w-full" required/></UFormField>
              <UFormField label="Adresse e-mail" required><UInput v-model="state.email" type="email" placeholder="vous@exemple.com" icon="i-lucide-mail" size="xl" class="w-full" required/></UFormField>
              <UFormField label="Objet"><USelect v-model="state.subject" :items="subjects" size="xl" class="w-full"/></UFormField>
              <UFormField label="Message" required><UTextarea v-model="state.message" :rows="5" placeholder="Votre message..." class="w-full" required/></UFormField>
              <UButton type="submit" block size="xl">Préparer mon message</UButton>
            </form>
          </UCard>
        </div>
      </UContainer>
    </section>
  </div>
</template>