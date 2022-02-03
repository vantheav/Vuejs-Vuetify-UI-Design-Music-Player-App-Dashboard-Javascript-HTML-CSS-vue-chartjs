<template>
  <section
    app
    color="#0F0A1E"
    mini-variant
    mini-variant-width="90"
  >
    <v-avatar class="d-block text-center mx-auto mt-4" size="60">
      <v-icon color="#C3F942" x-large>fab fa-soundcloud</v-icon>
    </v-avatar>
    <v-list flat class="mt-16" >
      <v-list-item-group>
        <v-list-item active-class="border" v-slot="{ active }" :to="{ path: '/' }">
          <v-list-item-content>
            <v-icon :color="active ? '#C3F942' : 'grey'">mdi-developer-board</v-icon>
          </v-list-item-content>
        </v-list-item>
        <v-list-item active-class="border" v-slot="{ active }" :to="{ path: '/about' }">
          <v-list-item-content>
            <v-icon :color="active ? '#C3F942' : 'grey'">fas fa-podcast</v-icon>
          </v-list-item-content>
        </v-list-item>
        <v-list-item active-class="border" v-slot="{ active }" :to="{ path: '/music' }">
          <v-list-item-content>
            <v-icon :color="active ? '#C3F942' : 'grey'">fas fa-music</v-icon>
          </v-list-item-content>
        </v-list-item>
        <v-list-item active-class="border" v-slot="{ active }">
          <v-list-item-content>
            <v-icon :color="active ? '#C3F942' : 'grey'">far fa-bell</v-icon>
          </v-list-item-content>
        </v-list-item>
        <v-list-item active-class="border" v-slot="{ active }">
          <v-list-item-content>
            <v-icon :color="active ? '#C3F942' : 'grey'">fas fa-search-dollar </v-icon>
          </v-list-item-content>
        </v-list-item>
        <v-list-item active-class="border" v-slot="{ active }">
          <v-list-item-content>
            <v-icon :color="active ? '#C3F942' : 'grey'">far fa-user</v-icon>
          </v-list-item-content>
        </v-list-item>
      </v-list-item-group>
    </v-list>
    <div
      style="
        position: absolute;
        bottom: 20px;
        margin-left: auto;
        margin-right: auto;
        left: 0;
        right: 0;
        text-align: center;
      "
    >
      <v-icon color="grey">far fa-question-circle</v-icon>
    </div>
  </section>
</template>

<script scoped>
export default {
  data: () => ({
    // selectedItem: 0,
    drawer: null,
  }),
};
</script>

<style>
.border {
  text-decoration: none;
  text-shadow: 1px 1px 2px black, 0 0 15px #c3f942, 0 0 5px green;
}
.v-list-item-group .v-list-item--active {
  color: #c3f942 !important;
}
</style>