<template>
  <div id="app">
    <NavBar />
    <Landing />

    <Vendeghaz />
    <Apartmanok />
  </div>
</template>

<script>
import NavBar from "@/components/nav-bar";
import Landing from "@/components/landing";
import Vendeghaz from "@/views/vendeghaz";
import Apartmanok from "@/views/apartmanok";

export default {
  name: "App",
  components: { NavBar, Landing, Vendeghaz, Apartmanok },
};
</script>

<style>
@import "design/main.css";
</style>
