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
          <a href="#bemutatkozas">Bemutatkozás</a>
        </li>

        <li class="nav-item">
          <a href="#szobak">Szobák</a>
        </li>

        <li class="nav-item">
          <a href="#foglalas">Foglalás</a>
        </li>

        <li class="nav-item">
          <a href="#extrak">Extrák</a>
        </li>

        <li class="nav-item">
          <a href="#galeria">Galéria</a>
        </li>

        <li class="nav-item">
          <a href="#kapcsolat">Kapcsolat</a>
        </li>

        <li class="nav-item">
          <button type="button" class="btn btn-kisfaludy" data-toggle="modal" data-target="#ModalKisfaludy">Kisfaludy</button>
        </li>
      </ul>

      <div class="form-inline my-2 my-lg-0">
        <button
          class="btn btn btn-outline-light mybutton"
          style="font-weight: bold;">
          <a href="#foglalas">
          Foglalás</a>
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