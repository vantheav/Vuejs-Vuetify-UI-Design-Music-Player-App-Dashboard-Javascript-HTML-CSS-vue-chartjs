<template>
  <v-app :style="{background: $vuetify.theme.themes.dark.background}">
    <!-- <RightSideBar /> -->
    <Dashboard />
  </v-app>
</template>

<script>
  // import RightSideBar from '../components/RightSideBar'
  import Dashboard from '../components/Dashboard'

  export default {
    name: 'Home',
    components: {
      // RightSideBar,
      Dashboard
      
    },
  }
</script>
