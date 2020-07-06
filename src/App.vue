<template>
  <v-app>
    <Header :links="links" />
    <v-main>
      <router-view></router-view>
    </v-main>
    <Footer :links="links" />
  </v-app>
</template>

<script>
import Footer from './components/Footer';
import Header from './components/Header';

export default {
  name: 'App',
  components: { Header, Footer },
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
