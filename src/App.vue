<template>


<v-app>
    <v-navigation-drawer app color="#0F0A1E" mini-variant mini-variant-width="90">
      <SideBar></SideBar>
  </v-navigation-drawer>

  <v-navigation-drawer app clipped right color="#0F0A1E">
     <rightBar></rightBar>
  </v-navigation-drawer>

  <v-main>
      <router-view></router-view>
  </v-main>
</v-app>

</template>

<script>
import rightBar from './components/RightSideBar.vue'
import SideBar from './components/SideBar.vue';

export default {
  name: 'App',
  components: {
    SideBar,
    rightBar,
  },

  data: () => ({
    //
  }),
};
</script>
  