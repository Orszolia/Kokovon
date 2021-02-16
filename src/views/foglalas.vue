<template>
  <div class="container">
    <div class="container page foglalas">
      <h1 class="display-1">Foglalj</h1>
      <h1 class="display-2">nálunk!</h1>

      <div class="row">
        <div class="col-4">
          <span class="calendar"> </span>
        </div>

        <div class="col-8">
          <form>
            <div class="row">
              <div class="col-5">
                <div class="form-group">
                  <label for="inputEmail">E-mail címed:</label>
                  <input
                    type="email"
                    class="form-control"
                    id="inputEmail"
                    placeholder="E-mail"
                  />
                </div>

                <div class="form-group">
                  <label for="inputName">Neved:</label>
                  <input
                    type="text"
                    class="form-control"
                    id="inputName"
                    placeholder="Nev"
                  />
                </div>

                <div class="form-group">
                  <label for="inputRooms">Szobák:</label>
                  <input
                    type="text"
                    class="form-control"
                    id="inputRooms"
                    placeholder=""
                  />
                </div>

                <div class="form-group">
                  <label for="inputMessage">Üzeneted:</label>
                  <textarea
                    class="form-control"
                    id="inputMessage"
                    rows="3"
                  ></textarea>
                </div>
              </div>

              <div class="col-7">
                <div class="form-row">
                  <div class="form-group col">
                    <label for="inputAdults">Felnőtt:</label>
                    <div class="form-inline">
                      <button class="btn btn-light">
                        <img class="add" src="../assets/images/minus.svg" />
                      </button>
                      <input
                        type="text"
                        class="form-control xs-1"
                        id="inputAdults"
                        style="width: 40px"
                      />
                      <button class="btn btn-light">
                        <img class="add" src="../assets/images/plus.svg" />
                      </button>
                    </div>
                  </div>

                  <div class="form-group col">
                    <label for="inputChildren">Gyerek:</label>
                    <div class="form-inline">
                      <button class="btn btn-light">
                        <img class="add" src="../assets/images/minus.svg" />
                      </button>
                      <input
                        type="text"
                        class="form-control xs-1"
                        id="inputChildren"
                        style="width: 40px"
                      />
                      <button class="btn btn-light">
                        <img class="add" src="../assets/images/plus.svg" />
                      </button>
                    </div>
                  </div>
                </div>

                <div class="form-row">
                  <div class="form-group col">
                    <label for="start">Érkezés:</label>

                    <input
                      type="date"
                      id="start"
                      name="trip-start"
                      value="2020-03-01"
                      min="2020-01-01"
                      max="2020-12-31"
                    />
                  </div>

                  <div class="form-group col">
                    <label for="start">Távozás:</label>

                    <input
                      type="date"
                      id="end"
                      name="trip-end"
                      value="2020-03-01"
                      min="2020-01-01"
                      max="2020-12-31"
                    />
                  </div>
                </div>

                <p class="hiba hide">
                  Ebben az időszakban a minimális foglalás 2 éjszaka.
                </p>

                <h5 class="extrak:">Extrák</h5>

                <div class="row">
                  <div class="col">
                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="inlineCheckbox1"
                        value="option1"
                      />
                      <label class="form-check-label" for="inlineCheckbox1"
                        >Biciklik</label
                      >
                    </div>

                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="inlineCheckbox1"
                        value="option1"
                      />
                      <label class="form-check-label" for="inlineCheckbox1"
                        >Dézsa</label
                      >
                    </div>
                  </div>
                </div>

                <div class="row">
                  <div class="col">
                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="inlineCheckbox1"
                        value="option1"
                      />
                      <label class="form-check-label" for="inlineCheckbox1"
                        >Babaágy</label
                      >
                    </div>

                    <div class="form-check form-check-inline">
                      <input
                        class="form-check-input"
                        type="checkbox"
                        id="inlineCheckbox1"
                        value="option1"
                      />
                      <label class="form-check-label" for="inlineCheckbox1"
                        >Grill</label
                      >
                    </div>
                  </div>
                </div>

                <button type="button kuldes" class="btn btn-dark mt-5 btn-lg">
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