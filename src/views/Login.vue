<template>
      <v-main>
        <v-container style="max-width: 450px" fill-height>
          <v-layout align-center row wrap>
            <v-flex xs12>
              <v-card>
                <div class="pa-10">
                  <h1 style="text-align: center" class="mb-10">Login</h1>
                  <form>
                    <v-text-field
                      v-model="email"
                      label="Email"
                      :rules="emailRules"
                      prepend-inner-icon="mdi-account"
                    ></v-text-field>
                    <v-btn
                      color="blue lighten-1 text-capitalize"
                      depressed
                      large
                      block
                      dark
                      class="mb-3"
                      @click = "login"
                    >
                      Login
                    </v-btn>
                    <v-btn
                      to = "/sign-up"
                      color="blue lighten-1 text-capitalize"
                      depressed
                      large
                      block
                      dark
                    >
                      Sign Up
                    </v-btn>
                  </form>
                </div>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
      </v-main>
  </template>

<script>
export default {
  data: () => ({
      valid: false,
      email: '',
      emailRules: [
        v => !!v || 'E-mail is required',
        v => /.+@.+/.test(v) || 'E-mail must be valid',
      ],
    }),
  methods:{
    login(){
      console.log(email)
    }
  }
}
</script>

<style>

</style>