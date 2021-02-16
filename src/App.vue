<template>
  <div id="app">
    <NavBar />
    <Landing />

    <Vendeghaz />
    <Apartmanok />
    <Foglalas />
  </div>
</template>

<script>
import NavBar from "@/components/nav-bar";
import Landing from "@/components/landing";
import Vendeghaz from "@/views/vendeghaz";
import Apartmanok from "@/views/apartmanok";
import Foglalas from "@/views/foglalas";

export default {
  name: "App",
  components: { NavBar, Landing, Vendeghaz, Apartmanok, Foglalas },
};
</script>

<style>
@import "design/main.css";
</style>
