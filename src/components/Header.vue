<template>
  <v-app-bar app color="primary" dark>
    <v-toolbar-title>Investalyzer</v-toolbar-title>
    <v-spacer />
    <v-btn v-for="link in links" :key="`${link.label}-header-link`" text rounded :to="link.url">
      {{ link.label }}
    </v-btn>
  </v-app-bar>
</template>
<script>
export default {
  name: 'Header',
  props: {
    links: {}
  }
};
</script>
