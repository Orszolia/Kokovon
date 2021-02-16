<template>
  <div>
    <div class="Sir_David" :style="selectedRoom.background">
      <div class="room_container page szobak">
        <div class="container">
          <div class="row">
            <div class="col-1 arrow">
              <button class="btn" @click="previousRoom()">
                <img src="../assets/images/arrow2.svg" />
              </button>
            </div>

            <div class="col" style="padding-left: 50px">
              <button class="szobainfo btn btn-outline-light">
                FOGLALD LE MOST!
              </button>

              <button
                class="szobainfo btn btn-outline-light"
                data-toggle="modal"
                data-target=".bg-modal-lg"
              >
                FEDEZD FEL A SZOBÁT!
              </button>

              <h1 class="display-1" style="color: white">
                {{ selectedRoom.roomName }}
              </h1>
              <h1 class="display-2" style="color: white">
                {{ selectedRoom.roomType }}
              </h1>

              <div class="row">
                <div class="col" v-if="selectedRoom.roomIcons.includes('bed')">
                  <div class="icon_opacity bed">
                    <img src="../assets/images/bed.png" />
                  </div>
                </div>

                <div
                  class="col"
                  v-if="selectedRoom.roomIcons.includes('singlebed')"
                >
                  <div class="icon_opacity singlebed">
                    <img src="../assets/images/singlebed.svg" />
                  </div>
                </div>

                <div class="col" v-if="selectedRoom.roomIcons.includes('wifi')">
                  <div class="icon_opacity wifi">
                    <img src="../assets/images/wifi.svg" />
                  </div>
                </div>

                <div
                  class="col"
                  v-if="selectedRoom.roomIcons.includes('fridge')"
                >
                  <div class="icon_opacity fridge">
                    <img src="../assets/images/fridge.svg" />
                  </div>
                </div>

                <div class="col" v-if="selectedRoom.roomIcons.includes('ac')">
                  <div class="icon_opacity ac">
                    <img src="../assets/images/ac.svg" />
                  </div>
                </div>

                <div
                  class="col"
                  v-if="selectedRoom.roomIcons.includes('bathroom')"
                >
                  <div class="icon_opacity bathroom">
                    <img src="../assets/images/bathroom.svg" />
                  </div>
                </div>

                <div
                  class="col"
                  v-if="selectedRoom.roomIcons.includes('calendar')"
                >
                  <div class="icon_opacity calendar">
                    <img src="../assets/images/calendar.svg" />
                  </div>
                </div>
              </div>
            </div>

            <div class="col-1 arrow">
              <button class="btn" @click="nextRoom()">
                <img src="../assets/images/arrow1.svg" />
              </button>
            </div>
          </div>
        </div>
      </div>
    </div>

    <ApartmanModal :room="selectedRoom" />
  </div>
</template>

<script>
const Rooms = [
  {
    id: 1,
    roomName: "Sir David",
    background: {
      backgroundImage: `url(${require("../assets/images/sirdavid_background.jpg")})`,
    },
    roomType: "apartman",
    roomIcons: ["bed", "wifi", "fridge", "bathroom", "calendar"],
  },
  {
    id: 2,
    roomName: "Maui",
    background: {
      backgroundImage: `url(${require("../assets/images/maui_bg.jpg")})`,
    },
    roomType: "apartman",
    roomIcons: ["bed", "wifi", "fridge", "bathroom", "ac"],
  },
  {
    id: 3,
    roomName: "Herr Mayer",
    background: {
      backgroundImage: `url(${require("../assets/images/herrmayer_bg.jpg")})`,
    },
    roomType: "apartman",
    roomIcons: ["bed", "singlebed", "fridge", "bathroom", "calendar"],
  },
  {
    id: 4,
    roomName: "Deluxe",
    background: {
      backgroundImage: `url(${require("../assets/images/herrmayer_bg.jpg")})`,
    },
    roomType: "sátor",
    roomIcons: ["bed", "singlebed", "bathroom", "calendar"],
  },
];

import ApartmanModal from "@/components/apartman-modal";

export default {
  name: "Rooms",
  components: { ApartmanModal },
  data() {
    return {
      rooms: Rooms,
      selectedRoom: {
        id: 1,
        roomName: "Sir David",
        background: {
          backgroundImage: `url(${require("../assets/images/sirdavid_background.jpg")})`,
        },
        roomType: "apartman",
        roomIcons: ["bed", "wifi", "fridge", "bathroom", "calendar"],
      },
    };
  },
  created() {},
  methods: {
    nextRoom() {
      var selectedRoomId = this.selectedRoom.id + 1;
      if (selectedRoomId <= Rooms.length) {
        var selectedRoom = Rooms.find((room) => room.id == selectedRoomId);
        this.selectedRoom = selectedRoom;
      } else {
        selectedRoomId = 1;
        selectedRoom = Rooms.find((room) => room.id == selectedRoomId);
        this.selectedRoom = selectedRoom;
      }
    },
    previousRoom() {
      var selectedRoomId = this.selectedRoom.id - 1;
      if (selectedRoomId > 0) {
        var selectedRoom = Rooms.find((room) => room.id == selectedRoomId);
        this.selectedRoom = selectedRoom;
      } else {
        selectedRoomId = Rooms.length;
        selectedRoom = Rooms.find((room) => room.id == selectedRoomId);
        this.selectedRoom = selectedRoom;
      }
    },
  },
};
</script>