<template>
  <header>
    <nav
      class="navbar navbar-expand-lg navbar navbar-dark bg-dark fixed-top"
      style="opacity: 0.8"
    >
      <NavBarLinks></NavBarLinks>
    </nav>
  </header>
</template>

<script>
import NavBarLinks from "@/components/nav-bar-links";

export default {
  name: "NavBar",
  components: { NavBarLinks },
};
</script>

