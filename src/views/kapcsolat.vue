<template>
  <section id="kapcsolat">
    <div
      class="kapcsolat"
      :style="{
        'background-image': `url(${require('../assets/images/kapcsolat.jpg')})`,
      }"
    >
      <div class="page">
        <div class="kapcsolat_blur">
          <div class="container">
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
                <div class="col-6">
                  <div class="form-group">
                    <label for="inputName" style="color: whitesmoke"
                      >Neved:</label
                    >
                    <input
                      v-model="name"
                      type="text"
                      class="form-control"
                      id="inputName"
                      placeholder="Név"
                      required
                    />
                  </div>

                  <div class="form-group">
                    <label for="inputEmail" style="color: whitesmoke"
                      >E-mail címed:</label
                    >
                    <input
                      v-model="email"
                      type="email"
                      class="form-control"
                      id="inputEmail"
                      placeholder="E-mail"
                      required
                    />
                  </div>

                  <div class="form-group">
                    <label for="inputMessage" style="color: whitesmoke"
                      >Üzeneted:</label
                    >
                    <textarea
                      class="form-control"
                      id="inputMessage"
                      rows="3"
                      v-model="message"
                      required
                    ></textarea>
                  </div>
                </div>
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
export default {
  name: "Kapcsolat",
};
</script>