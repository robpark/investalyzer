<template>
  <v-app>
    <Header2 :links="links" />
    <v-main>
      <router-view></router-view>
    </v-main>
    <Footer :links="links" />
  </v-app>
</template>

<script>
import Footer from './components/Footer';
import Header2 from './components/Header';

export default {
  name: 'App',
  components: { Header2, Footer },
  data() {
    return {
      links: [
        {
          label: 'Home',
          url: '/'
        },
        {
          label: 'Login',
          url: '/login'
        },
        {
          label: 'Investments',
          url: '/investments'
        }
      ]
    };
  }
};
</script>
