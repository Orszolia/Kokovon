<template>
  <div
    class="Sir_David"
    :style="{
      'background-image': `url(${require('../assets/images/sirdavid_background.jpg')})`,
    }"
  >
    <div class="room_container page szobak">
      <div class="container">
        <div class="row">
          <div class="col-1 arrow">
            <a href="">
              <img src="../assets/images/arrow2.svg" />
            </a>
          </div>

          <div class="col" style="padding-left: 50px">
            <button class="szobainfo btn btn-outline-light">
              FOGLALD LE MOST!
            </button>

            <button class="szobainfo btn btn-outline-light">
              FEDEZD FEL A SZOBÁT!
            </button>

            <h1 class="display-1" style="color: white">Sir David</h1>
            <h1 class="display-2" style="color: white">Apartman</h1>

            <div class="row">
              <div class="col">
                <div class="icon_opacity bed">
                  <img src="../assets/images/bed.png" />
                </div>
              </div>

              <div class="col hidden">
                <div class="icon_opacity singlebed">
                  <img src="../assets/images/singlebed.svg" />
                </div>
              </div>

              <div class="col">
                <div class="icon_opacity wifi">
                  <img src="../assets/images/wifi.svg" />
                </div>
              </div>

              <div class="col">
                <div class="icon_opacity fridge">
                  <img src="../assets/images/fridge.svg" />
                </div>
              </div>

              <div class="col hidden">
                <div class="icon_opacity ac">
                  <img src="../assets/images/ac.svg" />
                </div>
              </div>

              <div class="col">
                <div class="icon_opacity bathroom">
                  <img src="../assets/images/bathroom.svg" />
                </div>
              </div>

              <div class="col">
                <div class="icon_opacity calendar">
                  <img src="../assets/images/calendar.svg" />
                </div>
              </div>
            </div>
          </div>

          <div class="col-1 arrow">
            <a href="">
              <img src="../assets/images/arrow1.svg" />
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>