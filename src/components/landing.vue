<template>
  <div
    class="landing"
    :style="{
      'background-image': `url(${require('../assets/images/landing_background.jpg')})`,
    }"
  >
    <div class="logo_container text-center">
      <img class="mainlogo" src="../assets/images/logo_house.png" alt="logo" />
    </div>
  </div>
</template>

<script>
export default {
  name: "Landing",
};
</script>