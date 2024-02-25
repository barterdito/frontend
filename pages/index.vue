<template>
  <!-- <div class="background-landing" :style="{backgroundImage: `url($ {image})`}"> -->
    <img v-if="mdAndUp" class="background-landing" src="~/assets/bg-1920.jpg" />
    <img v-else class="background-landing " src="~/assets/bg-mobile.jpg" />
  <!-- </div> -->
</template>

<script setup>
  import { useDisplay } from 'vuetify'

  // Destructure only the keys you want to use
  const { xs, mdAndUp } = useDisplay()
</script>

<style scoped>
.background-landing {
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  background-size:cover;
  background-position: center;
}

</style>