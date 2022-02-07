<template>
  <div
    class="modal fade bg-modal-lg"
    tabindex="-1"
    role="dialog"
    aria-labelledby="myLargeModalLabel"
    aria-hidden="true"
  >
    <div class="modal-dialog modal-dialog-apartman modal-lg">
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

          <h1 class="display-3" style="margin-left: 100px">
            {{ room.roomName }}
          </h1>
          <h1 class="display-4">{{ room.roomType }}</h1>

          <div class="row justify-content-center">
            <div class="modal_col col-sm-auto">
              <img
                class="sirdavid_photo"
                :src="room.image1"
                alt="apartmanphoto1"
              /><br />
              <img class="sirdavid_photo" :src="room.image2" alt="" />
            </div>

            <div class="modal_col col-sm-auto">
              <img class="sirdavid_photo2" :src="room.image3" alt="" />
            </div>

            <div class="modal_col col-sm-auto">
              <p class="arak">árak</p>
              <table class="table table-bordered">
                <tbody>
                  <tr>
                    <td>Főszezon (jún.15.-aug.31.)</td>
                    <td v-if="room.id < 4">24 000,- Ft</td>
                    <td v-else>20 000,- Ft</td>
                  </tr>
                  <tr>
                    <td v-if="room.id < 4">
                      Elő-/utószezon (ápr.1.-jún.14., szept.1-okt.31.)
                    </td>
                    <td v-if="room.id < 4">24 000,- Ft</td>
                  </tr>
                  <tr>
                    <td v-if="room.id < 4">
                      Szezonon kívül (nov.01.-márc.31.)
                    </td>
                    <td v-if="room.id < 4">22 000,- Ft</td>
                  </tr>
                  <tr v-if="room.id === 3">
                    <td>Az árak két főre vonatkoznak, ezen felül</td>
                    <td>+5 000,- Ft fejenként</td>
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