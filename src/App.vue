<template>
  <div id="app">
    <NavBar />
    <Landing />

    <Vendeghaz />
    <Apartmanok />
    <Foglalas />
    
    <Extrak />
    <Galeria />
    <Kapcsolat />

  </div>
</template>

<script>
import NavBar from "@/components/nav-bar";
import Landing from "@/components/landing";
import Vendeghaz from "@/views/vendeghaz";
import Apartmanok from "@/views/apartmanok";
import Foglalas from "@/views/foglalas";
import Extrak from "@/views/extrak";
import Galeria from "@/views/galeria";
import Kapcsolat from "@/views/kapcsolat";

export default {
  name: "App",
  components: { NavBar, Landing, Vendeghaz, Apartmanok, Foglalas, Extrak, Galeria, Kapcsolat },
};
</script>

<style>
@import "design/main.css";
</style>
