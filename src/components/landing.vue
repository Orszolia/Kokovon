<template>
<div>
  
  <div
    class="landing landing_web"
    :style="{
      'background-image': `url(${require('../assets/images/landing/landing_background.jpg')})`,
    }"
  >
    <div class="logo_container text-center">
      <img class="mainlogo" src="../assets/images/landing/logo_house.png" alt="logo" />
    </div>
  </div>


</div>
</template>

<script>
export default {
  name: "Landing",
};
</script>