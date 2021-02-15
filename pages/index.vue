<template>
  <div class="container">
    <Header />
    <main class="main">
      <Profile />
      <Repository />
    </main>
    <Footer />
  </div>
</template>

<script>
import axios from "axios";
import Repository from "~/components/Repository.vue";
import Header from "~/components/Header.vue";
import Profile from "../components/Profile.vue";
import Footer from "../components/Footer.vue";

export default {
  components: {
    Repository,
    Header,
    Profile,
    Footer,
  }
};
</script>

<style>
</style>
