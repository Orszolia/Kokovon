<template>
  <section id="kapcsolat">
    <div
      class="kapcsolat"
      :style="{
        'background-image': `url(${require('../assets/images/kapcsolat.jpg')})`,
      }"
    >
      <div>
        <div class="kapcsolat_blur">
          <div class="container" style="padding-bottom: 100px">
            <h1 class="display-1 white" style="color: whitesmoke">
              Lépj velünk
            </h1>
            <h1 class="display-2 white" style="color: whitesmoke">
              kapcsolatba!
            </h1>

            <div class="row">
              <div class="col kapcsolat_box">
                <img
                  src="../assets/images/kapcsolat/phone.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">+36/70-339-4465</p>

                <img
                  src="../assets/images/kapcsolat/email.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">kokovon@kokovon.com</p>

                <img
                  src="../assets/images/kapcsolat/facebook.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">Kőkövön Vendégház</p>

                <img
                  src="../assets/images/kapcsolat/instagram.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">kokovon_vendeghaz</p>

                <img
                  src="../assets/images/kapcsolat/maps.png"
                  class="rounded float-left"
                  alt="..."
                />
                <p class="kapcsolat_text">
                  8230 Balatonfüred, Bajcsy-Zsilinszky u. 28.
                </p>
              </div>

              <div class="col kapcsolat_box">
                <form @submit.prevent="sendContact">
                  <div class="col-6">
                    <div class="form-group">
                      <label for="inputName" style="color: whitesmoke"
                        >Neved:</label
                      >
                      <input
                        v-model="contact_name"
                        type="text"
                        class="form-control"
                        id="contactInputName"
                        placeholder="Név"
                        name="contact_name"
                        required
                      />
                    </div>

                    <div class="form-group">
                      <label for="inputEmail" style="color: whitesmoke"
                        >E-mail címed:</label
                      >
                      <input
                        v-model="contact_email"
                        type="email"
                        class="form-control"
                        id="contactInputEmail"
                        placeholder="E-mail"
                        name="contact_email"
                        required
                      />
                    </div>

                    <div class="form-group">
                      <label for="inputMessage" style="color: whitesmoke"
                        >Üzeneted:</label
                      >
                      <textarea
                        class="form-control"
                        id="contactInputMessage"
                        rows="3"
                        v-model="contact_message"
                        name="contact_message"
                        required
                      ></textarea>
                    </div>
                    <button
                      type="button kuldes submit"
                      class="btn btn-dark mt-4 btn-lg"
                    >
                      Küldés
                    </button>
                    <div
                      class="alert"
                      role="alert"
                      style="margin: 10px 0px"
                      id="contact_alert"
                    ></div>
                  </div>
                </form>
              </div>

              <div class="col kapcsolat_box">
                <img
                  src="../assets/images/kapcsolat/quote_top.png"
                  class="quote_top"
                  alt="..."
                />
                <p class="rolunk">Rólunk mondták</p>
                <p class="velemeny">
                  Csodás. Egyszerűen csodás. Béke van, romantika van, nyugalom
                  van, bicikli van, és csupa-csupa apró figyelmesség, kedvesség,
                  mindenhol. Nagyon szerettük!
                </p>
                <img
                  src="../assets/images/kapcsolat/quote_bottom.png"
                  class="quote_bottom"
                  alt="..."
                />
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
import emailjs from "emailjs-com";

export default {
  name: "Kapcsolat",

  data() {
    return {
      contact_name: undefined,
      contact_email: undefined,
      contact_message: undefined,
    };
  },
  methods: {
    sendContact(e) {
      try {
        emailjs.sendForm(
          "service_7l0rp2n",
          "template_4vn6c3f",
          e.target,
          "user_2fTzZBeA9lR7RMZjUkzge",
          {
            contact_name: this.contact_name,
            contact_email: this.contact_email,
            contact_message: this.contact_message,
          }
        );
        document
          .getElementById("contact_alert")
          .classList.remove("alert-danger");
        document.getElementById("contact_alert").classList.add("alert-success");
        document.getElementById("contact_alert").innerHTML = "Üzenet elküldve!";
        // Reset form field
        this.contact_name = undefined;
        this.contact_email = undefined;
        this.contact_message = undefined;
      } catch (error) {
        document.getElementById("contact_alert").classList.add("alert-danger");
        document.getElementById("contact_alert").innerHTML =
          "A küldés sikertelen, további informácóért hívd az alábbi telefonszámot: +36703394465";
      }
    },
  },
};
</script>