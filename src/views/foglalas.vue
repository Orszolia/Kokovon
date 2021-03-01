<template>
  <div class="container">
    <div class="container page foglalas">
      <h1 class="display-1">Foglalj</h1>
      <h1 class="display-2">nálunk!</h1>

      <div class="row">
        <div class="col-5" style="margin-bottom: 20px">
          <Calendar
            @get_arrival_date="get_arrival_date"
            @get_leave_date="get_leave_date"
            :room="selectedCalendarRoom"
            :hide="hide"
          />
        </div>

        <div class="col-6">
          <form>
            <div class="row">
              <div class="col-6">
                <div class="form-group">
                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="maui_input"
                      name="calendar_view"
                      value="Maui apartman"
                      v-model="rooms"
                    />
                    <label
                      class="form-check-label"
                      for="maui_input"
                      data-html="true"
                      >Maui apartman</label
                    >
                    <button
                      type="button"
                      class="btn btn-outline-danger eye_button hide_maui"
                      @click="removeData(true, 'maui'), newButton('maui')"
                    >
                      <i class="fas fa-eye-slash"></i>
                    </button>

                    <button
                      type="button"
                      class="btn btn-outline-danger eye_button show_maui hidden"
                      @click="removeData(false, 'maui'), newButton2('maui')"
                    >
                      <i class="fas fa-eye"></i>
                    </button>

                    <button
                      type="button"
                      class="btn btn-outline-dark i_button"
                      data-toggle="popover"
                      data-trigger="focus"
                      data-placement="right"
                      title="Maui apartman"
                      data-content="Foglalható 2 főre"
                    >
                      i
                    </button>
                  </div>

                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="sirdavid_input"
                      name="calendar_view"
                      value="Sir David apartman"
                      v-model="rooms"
                    />
                    <label class="form-check-label" for="sirdavid_input"
                      >Sir David apartman</label
                    >
                    <button
                      type="button"
                      class="btn btn-outline-warning eye_button hide_sirdavid"
                      @click="
                        removeData(true, 'sirdavid'), newButton('sirdavid')
                      "
                    >
                      <i class="fas fa-eye-slash"></i>
                    </button>

                    <button
                      type="button"
                      class="btn btn-outline-warning eye_button show_sirdavid hidden"
                      @click="
                        removeData(false, 'sirdavid'), newButton2('sirdavid')
                      "
                    >
                      <i class="fas fa-eye"></i>
                    </button>
                    <button
                      type="button"
                      class="btn btn-outline-dark i_button"
                      data-toggle="popover"
                      data-trigger="focus"
                      data-placement="right"
                      title="Sir David apartman"
                      data-content="Foglalható 2 főre"
                    >
                      i
                    </button>
                  </div>

                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="herrmayer_input"
                      name="calendar_view"
                      value="Herr Mayer apartman"
                      v-model="rooms"
                    />
                    <label class="form-check-label" for="herrmayer_input"
                      >Herr Mayer apartman</label
                    >
                    <button
                      type="button"
                      class="btn btn-outline-primary eye_button hide_herrmayer"
                      @click="
                        removeData(true, 'herrmayer'), newButton('herrmayer')
                      "
                    >
                      <i class="fas fa-eye-slash"></i>
                    </button>

                    <button
                      type="button"
                      class="btn btn-outline-primary eye_button show_herrmayer hidden"
                      @click="
                        removeData(false, 'herrmayer'), newButton2('herrmayer')
                      "
                    >
                      <i class="fas fa-eye"></i>
                    </button>
                    <button
                      type="button"
                      class="btn btn-outline-dark i_button"
                      data-toggle="popover"
                      data-trigger="focus"
                      data-placement="right"
                      title="Herr Mayer apartman"
                      data-content="Foglalható 4 főre"
                    >
                      i
                    </button>
                  </div>

                  <div class="form-check">
                    <input
                      class="form-check-input"
                      type="checkbox"
                      id="sator_input"
                      name="calendar_view"
                      value="Deluxe sátor"
                      v-model="rooms"
                    />
                    <label class="form-check-label" for="sator_input"
                      >Deluxe Sátor</label
                    >
                    <button
                      type="button"
                      class="btn btn-outline-success eye_button hide_sator"
                      @click="removeData(true, 'sator'), newButton('sator')"
                    >
                      <i class="fas fa-eye-slash"></i>
                    </button>

                    <button
                      type="button"
                      class="btn btn-outline-success eye_button show_sator hidden"
                      @click="removeData(false, 'sator'), newButton2('sator')"
                    >
                      <i class="fas fa-eye"></i>
                    </button>
                    <button
                      type="button"
                      class="btn btn-outline-dark i_button"
                      data-toggle="popover"
                      data-trigger="focus"
                      data-placement="right"
                      title="Deluxe sátor"
                      data-content="Foglalható 4 főre"
                    >
                      i
                    </button>
                  </div>
                </div>

                <div class="form-row">
                  <div class="form-group col">
                    <label for="start">Érkezés:</label>
                    <datepicker
                      id="start_input"
                      v-model="arrival"
                      :language="hu"
                      :monday-first="true"
                      :format="formatDate"
                      :full-month-name="true"
                      :disabled-dates="state.disabledDates"
                      style="width: 100px"
                    ></datepicker>
                  </div>

                  <div class="form-group col">
                    <label for="start">Távozás:</label>

                    <datepicker
                      id="end_input"
                      v-model="leave"
                      :language="hu"
                      :monday-first="true"
                      :format="formatDate"
                      :full-month-name="true"
                      :disabled-dates="state.disabledDates"
                      :orientation="left"
                    ></datepicker>
                  </div>
                </div>

                <p class="hiba hide">
                  Ebben az időszakban a minimális foglalás 2 éjszaka.
                </p>

                <div class="form-group">
                  <label for="inputName">Neved:</label>
                  <input
                    v-model="name"
                    type="text"
                    class="form-control"
                    id="inputName"
                    placeholder="Nev"
                    required
                  />
                </div>
              </div>

              <div class="col-6">
                <div class="form-group">
                  <label for="inputEmail">E-mail címed:</label>
                  <input
                    v-model="email"
                    type="email"
                    class="form-control"
                    id="inputEmail"
                    placeholder="E-mail"
                    required
                  />
                </div>

                <div class="form-row">
                  <div class="form-group col">
                    <label for="inputAdults">Felnőtt:</label>
                    <div class="form-inline">
                      <input
                        type="number"
                        class="form-control xs-1"
                        id="inputAdults"
                        style="width: 70px"
                        v-model="adults"
                        value="1"
                        min="1"
                      />
                    </div>
                  </div>
                  <div class="form-group col">
                    <label for="inputChildren">Gyerek:</label>
                    <div class="form-inline">
                      <input
                        type="number"
                        class="form-control xs-1"
                        id="inputChildren"
                        style="width: 70px"
                        v-model="children"
                        value="0"
                        min="0"
                      />
                    </div>
                  </div>
                </div>

                <div class="form-group">
                  <label for="inputMessage">Üzeneted:</label>
                  <textarea
                    class="form-control"
                    id="inputMessage"
                    rows="3"
                    v-model="message"
                    required
                  ></textarea>
                </div>

                <h5 class="extrak:">Extrák</h5>

                <div class="row">
                  <div class="col">
                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="bicikli"
                        value="bicikli"
                        v-model="extra"
                      />
                      <label class="form-check-label" for="bicikli"
                        >Biciklik</label
                      >
                    </div>

                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="dezsa"
                        value="dézsa"
                        v-model="extra"
                      />
                      <label class="form-check-label" for="dezsa">Dézsa</label>
                    </div>
                  </div>
                </div>

                <div class="row">
                  <div class="col">
                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="babaagy"
                        value="babaágy"
                        v-model="extra"
                      />
                      <label class="form-check-label" for="babaagy"
                        >Babaágy</label
                      >
                    </div>

                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="grill"
                        value="grill"
                        v-model="extra"
                      />
                      <label class="form-check-label" for="grill">Grill</label>
                    </div>
                  </div>
                </div>

                <button type="button kuldes" class="btn btn-dark mt-4 btn-lg">
                  Küldés
                </button>
              </div>
            </div>
          </form>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
var state = {
  disabledDates: {
    to: new Date(),
  },
};

import Calendar from "../components/calendar";
import Datepicker from "vuejs-datepicker";
import { hu } from "vuejs-datepicker/dist/locale";
import moment from "moment";

export default {
  name: "Foglalas",
  components: { Calendar, Datepicker },

  data() {
    return {
      name: undefined,
      email: undefined,
      rooms: [],
      message: undefined,
      adults: 1,
      children: 0,
      arrival: undefined,
      leave: undefined,
      extra: [],
      hu: hu,
      selectedCalendarRoom: undefined,
      hide: false,
      state: state,
    };
  },
  created() {
    this.getNextDays();
  },
  methods: {
    getNextDays() {
      var today = new Date();
      var tomorrow = new Date(today);
      tomorrow.setDate(tomorrow.getDate() + 1);
      var after_tomorrow = new Date(today);
      after_tomorrow.setDate(after_tomorrow.getDate() + 2);
      this.arrival = tomorrow;
      this.leave = after_tomorrow;
    },
    formatDate(date) {
      return moment(date).format("YYYY-MM-DD");
    },
    get_arrival_date(date) {
      this.arrival = date;
    },
    get_leave_date(date) {
      this.leave = date;
    },
    removeData(hide, room) {
      this.selectedCalendarRoom = room;
      this.hide = hide;
    },
    newButton(room) {
      document
        .getElementsByClassName("show_" + room)[0]
        .classList.remove("hidden");
      document
        .getElementsByClassName("hide_" + room)[0]
        .classList.add("hidden");
    },
    newButton2(room) {
      document
        .getElementsByClassName("hide_" + room)[0]
        .classList.remove("hidden");
      document
        .getElementsByClassName("show_" + room)[0]
        .classList.add("hidden");
    },
  },
};
</script>

<style>
.eye_button {
  border-radius: 50%;
  margin-left: 10px;
  font-size: 13px;
  padding: 1px 3px;
}

.i_button {
  border-radius: 50%;
  margin-left: 5px;
  font-size: 14px;
  padding: 0px 8px;
}
</style>