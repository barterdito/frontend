<template>
    <v-col v-if="mdAndUp" cols="3" xl="4" class="pl-0 pr-5">
        <v-row align-center>
            <v-col xl="6" lg="12" sm="12">
                <v-card class="px-6 py-8">
                    <v-form
                        v-model="form"
                    >
                        <v-text-field
                            class="mb-4"
                            label="Email"
                            variant="outlined"
                            color="primary"
                            hide-details
                            clearable
                        ></v-text-field>

                        <v-text-field
                            label="Password"
                            placeholder="Enter your password"
                            variant="outlined"
                            hide-details
                            color="primary"
                        ></v-text-field>

                        <br>

                        <v-btn
                            color="primary"
                            size="large"
                            type="submit"
                            variant="flat"
                            class="text-none"
                            block
                        >
                        Log In
                        </v-btn>

                        <br>

                        <v-btn
                            color="primary"
                            variant="text"
                            class="text-none"
                            block
                        >
                        Forgot Password?
                        </v-btn>

                        <br>

                        <v-divider></v-divider>

                        <br>

                        <v-btn
                            color="success"
                            size="large"
                            variant="flat"
                            class="text-none"
                            block
                        >
                        Register
                        </v-btn>
                    </v-form>
                </v-card>
            </v-col>
        </v-row>
    </v-col>
</template>

<script setup>
  import { useDisplay } from 'vuetify'

  const { smAndUp, mdAndUp } = useDisplay()

  const form = ref(null)

  useHead({
    title: 'Barterdito'
  })
</script>