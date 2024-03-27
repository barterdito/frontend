<template>
  <v-container class="pa-0" fluid>
    <v-row class="py-4">
      <SponsorCard />
      <BartersList />
      <LoginCard />
    </v-row>
  </v-container>
</template>

<script setup>
  import { useDisplay } from 'vuetify'

  import BartersList from '~/components/LandingPageComponents/BartersList.vue'
  import LoginCard from '~/components/LandingPageComponents/LoginCard.vue';
  import SponsorCard from '~/components/LandingPageComponents/SponsorCard'

  const isLoading = ref(true)

  const { smAndUp, mdAndUp } = useDisplay()

  useHead({
    title: 'Barterdito'
  })

  definePageMeta({
    layout: 'default'
  })

  onMounted(() => {
    setTimeout(() => {
      isLoading.value = false
    }, 500)
  })
</script>