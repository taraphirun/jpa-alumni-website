<template>
  <div>
    <!-- -----------------------------------------------
          Start Header
    ----------------------------------------------- -->
    <v-app-bar
      app
      class="app-header position-relative bg-dark header2"
      flat
    >
      <v-container class="py-0 fill-height">
        <!-- Logo -->
        <div class="logo">
          <NLink to="/">
            <v-img
              max-width="80px"
              :src="require('@/assets/images/logos/logo.jpeg')"
              alt="logo"
            />
          </NLink>
        </div>

        <v-spacer></v-spacer>
        <v-btn class="d-block d-md-none" text @click="toggleClass()">
          <v-app-bar-nav-icon />
        </v-btn>
        <!-- Desktop view Navigation -->
        <div
          class="navigation"
          v-bind:class="[isActive ? 'd-block' : '']"
          @click="isActive = !isActive"
        >
          <ul class="navbar-nav">
            <li class="nav-item" text>
              <n-link class="nav-link" nuxt to="/"> Class Year </n-link>
            </li>
            <li class="nav-item" text>
              <n-link class="nav-link" nuxt to="/about"> University </n-link>
            </li>
            <li class="nav-item" text>
              <n-link class="nav-link" nuxt to="/work"> Scholarship </n-link>
            </li>
            <li class="nav-item" text>
              <n-link class="nav-link" nuxt to="/services"> Career </n-link>
            </li>
          </ul>
        </div>
        <!-- login-regiter -->
        <v-btn
          class="d-none d-lg-flex btn-custom-nm ml-5"
          nuxt
          outlined
          color="primary"
          to="/"
          elevation="0"
        >
          Sign Up
        </v-btn>
      </v-container>
    </v-app-bar>
    <!-- -----------------------------------------------
          End Header
    ----------------------------------------------- -->
  </div>
</template>

<script>
export default {
  name: "Header1",
  data() {
    return {
      isActive: false,
    };
  },
  methods: {
    toggleClass: function (event) {
      this.isActive = !this.isActive;
    },
  },
};
</script>
