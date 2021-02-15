<template>
  <div class="container-fluid">
    <button
      class="navbar-toggler"
      type="button"
      data-toggle="collapse"
      data-target="#navbarSupportedContent"
      aria-controls="navbarSupportedContent"
      aria-expanded="false"
      aria-label="Toggle navigation"
    >
      <span class="navbar-toggler-icon"></span>
    </button>

    <div class="collapse navbar-collapse" id="navbarSupportedContent">
      <ul class="navbar-nav mr-auto">
        <li class="nav-item">
          <a class="nav-link" href="#">Szobák</a>
        </li>

        <li class="nav-item">
          <a class="nav-link" href="#">Galéria</a>
        </li>

        <li class="nav-item">
          <a class="nav-link" href="#">Extrák</a>
        </li>

        <li class="nav-item">
          <a class="nav-link" href="#">Ajánlások</a>
        </li>
      </ul>

      <div class="form-inline my-2 my-lg-0">
        <button
          class="btn btn btn-outline-light mybutton"
          style="font-weight: bold"
        >
          Foglalás
        </button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NavBarLinks",
};
</script>