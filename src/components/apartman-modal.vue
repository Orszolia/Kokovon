<template>
  <div
    class="modal fade bg-modal-lg"
    tabindex="-1"
    role="dialog"
    aria-labelledby="myLargeModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-apartman">
      <div class="modal-content">
        <div class="container-fluid sirdavid_foglalas">
          <button class="szobainfo btn btn-outline-dark">
            FOGLALD LE MOST!
          </button>

          <h1 class="display-3" style="margin-left: 100px">
            {{ room.roomName }}
          </h1>
          <h1 class="display-4">{{ room.roomType }}</h1>

          <p class="arak">árak</p>

          <div class="row justify-content-center">
            <div class="modal_col col-sm-auto">
              <img
                class="sirdavid_photo"
                src="../assets/images/modal/sirdavid_photo1.jpg"
                alt=""
              /><br />
              <img
                class="sirdavid_photo"
                src="../assets/images/modal/sirdavid_photo2.jpg"
                alt=""
              />
            </div>

            <div class="modal_col col-sm-auto">
              <img
                class="sirdavid_photo2"
                src="../assets/images/modal/sirdavid_photo3.jpeg"
                alt=""
              />
            </div>

            <div class="modal_col col-sm-auto">
              <table class="table table-bordered">
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

              <p class="aprobetus">Az árváltoztatás jogát fenntartjuk.</p>

              <p class="aprobetus">
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
  name: "ApartmanModal",
  props: {
    room: {
      type: Object,
      default: () => {},
    },
  },
};
</script>