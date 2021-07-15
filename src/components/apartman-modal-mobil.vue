<template>
  <div>
    <div
      class="modal fade bg-modal-sirdavid"
      id="bg-modal-sirdavid"
      tabindex="-1"
      role="dialog"
      aria-labelledby="myLargeModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-dialog-apartman">
        <div class="modal-content">
          <div class="container-fluid sirdavid_foglalas">
            <button
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>

            <h1 class="apartman_nev_mobil">Sir David</h1>
            <h1 class="apartman_nev2_mobil">Apartman</h1>

            <div class="modal_col col-sm-auto">
              <img
                class="sirdavid_photo2_mobil"
                src="../assets/images/modal/sirdavid_photo3.jpeg"
                alt="sirdavid"
              />
            </div>

            <div class="modal_col col-sm-auto">
              <table class="table_mobil table-bordered">
                <tbody>
                  <tr>
                    <td>Főszezon (jún.15.-aug.31.)</td>
                    <td>24 000,- Ft</td>
                  </tr>
                  <tr>
                    <td>Elő-/utószezon (ápr.1.-jún.14., szept.1-okt.31.)</td>
                    <td>20 000,- Ft</td>
                  </tr>
                  <tr>
                    <td>Szezonon kívül (nov.01.-márc.31.)</td>
                    <td>15 000,- Ft</td>
                  </tr>
                </tbody>
              </table>

              <p class="aprobetus_mobil">Az árváltoztatás jogát fenntartjuk.</p>

              <p class="aprobetus_mobil">
                Aktuális ajánlatainkért keressetek minket!
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div
      class="modal fade bg-modal-maui"
      id="bg-modal-maui"
      tabindex="-1"
      role="dialog"
      aria-labelledby="myLargeModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-dialog-apartman">
        <div class="modal-content">
          <div class="container-fluid sirdavid_foglalas">
            <button
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>

            <h1 class="apartman_nev_mobil">Maui</h1>
            <h1 class="apartman_nev2_mobil">Apartman</h1>

            <div class="modal_col col-sm-auto">
              <img
                class="sirdavid_photo2_mobil"
                src="../assets/images/galeria/maui6.jpg"
                alt="sirdavid"
              />
            </div>

            <div class="modal_col col-sm-auto">
              <table class="table_mobil table-bordered">
                <tbody>
                  <tr>
                    <td>Főszezon (jún.15.-aug.31.)</td>
                    <td>24 000,- Ft</td>
                  </tr>
                  <tr>
                    <td>Elő-/utószezon (ápr.1.-jún.14., szept.1-okt.31.)</td>
                    <td>20 000,- Ft</td>
                  </tr>
                  <tr>
                    <td>Szezonon kívül (nov.01.-márc.31.)</td>
                    <td>15 000,- Ft</td>
                  </tr>
                </tbody>
              </table>

              <p class="aprobetus_mobil">Az árváltoztatás jogát fenntartjuk.</p>

              <p class="aprobetus_mobil">
                Aktuális ajánlatainkért keressetek minket!
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>

    <div
      class="modal fade bg-modal-herrmayer"
      id="bg-modal-maui"
      tabindex="-1"
      role="dialog"
      aria-labelledby="myLargeModalLabel"
      aria-hidden="true"
    >
      <div class="modal-dialog modal-dialog-apartman">
        <div class="modal-content">
          <div class="container-fluid sirdavid_foglalas">
            <button
              type="button"
              class="close"
              data-dismiss="modal"
              aria-label="Close"
            >
              <span aria-hidden="true">&times;</span>
            </button>

            <h1 class="apartman_nev_mobil">Herr Mayer</h1>

            <h1 class="apartman_nev2_mobil">Apartman</h1>

            <div class="modal_col col-sm-auto">
              <img
                class="sirdavid_photo2_mobil"
                src="../assets/images/galeria/herrmayer2.jpeg"
                alt="sirdavid"
              />
            </div>

            <div class="modal_col col-sm-auto">
              <table class="table_mobil table-bordered">
                <tbody>
                  <tr>
                    <td>Főszezon (jún.15.-aug.31.)</td>
                    <td>24 000,- Ft</td>
                  </tr>
                  <tr>
                    <td>Elő-/utószezon (ápr.1.-jún.14., szept.1-okt.31.)</td>
                    <td>20 000,- Ft</td>
                  </tr>
                  <tr>
                    <td>Szezonon kívül (nov.01.-márc.31.)</td>
                    <td>15 000,- Ft</td>
                  </tr>
                </tbody>
              </table>

              <p class="aprobetus_mobil">Az árváltoztatás jogát fenntartjuk.</p>

              <p class="aprobetus_mobil">
                Aktuális ajánlatainkért keressetek minket!
              </p>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ApartmanModalMobil",
  props: {
    room: {
      type: Object,
      default: () => {},
    },
  },
};
</script>