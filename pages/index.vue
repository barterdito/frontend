<template>
    <div v-if="!isLoading">
      <img v-if="mdAndUp" class="background-landing" src="https://barterdito-bucket.s3.ap-southeast-1.amazonaws.com/bdito-assets/bg-1920.jpg" />
      <img v-if="smAndDown" class="background-landing" src="https://barterdito-bucket.s3.ap-southeast-1.amazonaws.com/bdito-assets/bg-mobile.jpg" />
    </div>
    <div v-else>
      <div class="background-landing" style="background-color: #FFFF00;"></div>
    </div>
</template>

<script setup>
  import { onMounted, ref } from 'vue'
  import { useDisplay } from 'vuetify'

  const isLoading = ref(true)

  // Destructure only the keys you want to use
  const { smAndDown, mdAndUp } = useDisplay()

  onMounted(() => {
    setTimeout(() => {
      isLoading.value = false
    }, 500)
  })
</script>

<style scoped>
.background-landing {
  height: 100vh;
  width: 100vw;
  display: flex;
  align-items: center;
  justify-content: center;
  background-size:auto;
  background-position: center;
}

</style>