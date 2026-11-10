<script setup lang="ts">
const state=reactive({name:'',email:'',subject:'Demande d’information',message:''})
const sent=ref(false)
const subjects=['Demande d’information','Coordination provinciale','Presse et médias','Partenariat','Autre demande']
useSeoMeta({title:'Contact | Force du Progrès'})
</script>
<template>
  <div>
    <PageHero title="Entrer en contact" description="Une question, une demande d’information ou une prise de contact institutionnelle ? Utilisez cet espace pour préparer votre message."/>
    <section class="content-section">
      <UContainer>
        <div class="contact-grid">
          <div>
            <div class="section-eyebrow">CONTACT ET INFORMATION</div>
            <h2 class="contact-title">Le dialogue commence ici.</h2>
            <p class="muted">Cet espace est destiné aux demandes d’information, aux échanges avec les médias et aux prises de contact des coordinations territoriales.</p>
            <div class="contact-detail"><UIcon name="i-lucide-map-pin"/><div><b>Coordination nationale</b><small>République démocratique du Congo</small></div></div>
            <div class="contact-detail"><UIcon name="i-lucide-newspaper"/><div><b>Presse et médias</b><small>Demandes d’information et de communication</small></div></div>
            <div class="contact-detail"><UIcon name="i-lucide-network"/><div><b>Coordinations territoriales</b><small>Échanges et renseignements organisationnels</small></div></div>
          </div>
          <UCard>
            <div v-if="sent" class="form-success">
              <UIcon name="i-lucide-check-circle"/><h3>Message préparé</h3>
              <p>Votre message est prêt. La transmission en ligne sera disponible lorsque le canal officiel sera connecté.</p>
              <UButton color="neutral" variant="outline" @click="sent=false">Rédiger un autre message</UButton>
            </div>
            <form v-else class="contact-form" @submit.prevent="sent=true">
              <h3>Écrire au portail</h3>
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