<template>
  <v-app>
    <v-app-bar app color="primary" dark>
      <v-toolbar-title>Investalyzer</v-toolbar-title>
      <v-spacer />
      <v-btn text rounded>Home</v-btn>
      <v-btn text rounded>Login</v-btn>
    </v-app-bar>
    <v-main>
      <!-- Login -->
      <v-card width="400" class="mx-auto mt-5">
        <v-card-title>
          <h1>Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form>
            <v-text-field label="Username" prepend-icon="mdi-account-circle" />
            <v-text-field type="password" label="Password" prepend-icon="mdi-lock" />
          </v-form>
        </v-card-text>
        <v-divider />
        <v-card-actions>
          <v-spacer />
          <v-btn color="info">Login</v-btn>
        </v-card-actions>
      </v-card>
    </v-main>
    <Footer />
  </v-app>
</template>

<script>
import Footer from './components/Footer';

export default {
  name: 'App',
  components: { Footer },
  data: () => ({
    //
  })
};
</script>
