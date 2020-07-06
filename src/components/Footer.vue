<template>
  <v-footer color="primary lighten-1" padless>
    <v-layout wrap align-center>
      <v-spacer />
      <v-btn v-for="link in links" :key="link" color="white" text rounded class="my-2">
        {{ link }}
      </v-btn>
      <v-flex primary lighten-2 py-4 text-center white--text xs12>
        4 Legs Software &copy;{{ new Date().getFullYear() }}
      </v-flex>
    </v-layout>
  </v-footer>
</template>

<script>
export default {
  name: 'Footer',

  data: () => ({
    links: ['Home', 'Login']
  })
};
</script>

<style scoped></style>
