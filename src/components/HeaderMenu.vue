<template>
  <div margin="auto" padding="auto">
    <v-app-bar color="deep-orange accent-4" dense dark >
      <v-toolbar-title > Stock Market </v-toolbar-title>
      <div  color="deep-orange accent-4" class="justify-space-between py-5 px-5">
      
      <v-btn alignLeft rounded color="warning" dark router-link to="/"
        >Home</v-btn
      >
      <v-btn rounded color="warning" dark router-link to="/logs">Logs</v-btn>
      </div>

      <v-spacer></v-spacer>
      <v-switch v-model="isAdmin" 
        :label="`Admin Status: ${isAdmin.toString()}`"></v-switch>
    </v-app-bar>
  </div>
</template>

<script>
import { mapMutations } from "vuex";

export default {
  name: "HeaderMenu",
  data: () => ({
    isAdmin: false,
  }),
  watch: {
    isAdmin(val) {
      this.SET_IS_ADMIN(val);
    },
  },
  methods: {
    ...mapMutations(["SET_IS_ADMIN"]),
  },
};
</script>

<style scoped>
h3 {
  margin: px 40 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>