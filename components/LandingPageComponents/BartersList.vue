<template>
    <v-col 
        ref="list"
        sm="12" md="6" xl="4" xs="12"
        style="height: 93vh; overflow: hidden;"
        class="px-0"
        :class="mdAndUp ? 'hide-scroll' : 'show-scroll'" 
        @mouseenter="showScroll"
        @mouseleave="hideScroll"
    >
        <v-card 
          v-for="i in 20" 
          :key="i" 
          :class="mdAndUp ? 'rounded-lg mx-2' : ' mx-1'"
          :flat="smAndDown"
          class="rounded-0 mb-4"
        >
          <v-col cols="6" md="4" xl="3">
            <v-row no-gutters>
              <v-col cols="3" sm="2" md="3" xl="3">
                <v-avatar
                    size="36px"
                  >
                    <v-img
                      alt="Avatar"
                      src="https://avatars0.githubusercontent.com/u/9064066?v=4&s=460"
                    ></v-img>
                </v-avatar>
              </v-col>
              <v-col> 
                <p class="mb-0 font-weight-bold">John Patrick</p>
                <p class="mb-0 text-caption text-disabled">1h</p>
              </v-col>
            </v-row>
          </v-col>
          <v-img
            class="align-end text-white"
            height="200"
            src="https://static.nike.com/a/images/f_auto/dpr_1.0,cs_srgb/w_773,c_limit/95e3c30f-aa7f-41a4-9959-8023fc707299/air-jordan-1-2022-lost-and-found-chicago-the-inspiration-behind-the-design.jpg"
            cover
          >
          </v-img>

          <v-card-title>
            Nike Shoes
          </v-card-title>

          <v-card-text>
            Ultimately, the team focused on several key design elements of the Chicago to drive the AJ1's history forwards. The image below shows the updated 2022 Chicago (top) next to an original 1985 Air Jordan 1 (bottom) to highlight the sneaker's inspiration.
          </v-card-text>

          <v-card-actions>
            <v-btn color="" icon="mdi-heart-outline" variant="text"></v-btn>
            <p class="mb-0">11</p>
            <BarterViewOne />
            <p class="mb-0">11</p>
            <v-spacer></v-spacer>
            <v-btn class="text-none" color="primary" variant="flat">
              + Create Offer
            </v-btn>
          </v-card-actions>
        </v-card>
    </v-col>
</template>

<script setup>
  import { useDisplay } from 'vuetify'
  import BarterViewOne from './BarterViewOne.vue';

  const { smAndDown, mdAndUp } = useDisplay()

  const list = ref(null)

  const showScroll = () => {
    list.value.$el.classList.add('show-scroll');
  }

  const hideScroll = () => {
    list.value.$el.classList.remove('show-scroll')
  }
</script>

<style scoped>
::-webkit-scrollbar {
    width: 8px;
    height: 8px;
  }

  ::-webkit-scrollbar-track {
    background: #EEEEEE;
    border-radius: 4px;
  }

  ::-webkit-scrollbar-thumb {
    background: #AEAEAE;
    border-radius: 10px;
    border-radius: 10px;
  }

  .show-scroll {
    overflow-y: auto !important;
  }

  .hide-scroll {
    overflow-y: hidden;
  }
</style>