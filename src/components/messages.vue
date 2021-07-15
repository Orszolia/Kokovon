<template>
  <div>
    <p class="hiba" v-if="thisSeason.min_nights > night_number">
      Ebben az időszakban a minimális foglalás két éjszaka.
    </p>
  </div>
</template>

<script>
const seasons = [
  {
    name: "Szezonon kínül",
    from: "01-01",
    to: "03-31",
    extra_price: 0,
    min_nights: 2,
  },
  {
    name: "Előszezon",
    from: "04-01",
    to: "06-14",
    extra_price: 0,
    min_nights: 2,
  },
  {
    name: "Főszezon",
    from: "06-15",
    to: "08-31",
    extra_price: 2000,
    min_nights: 3,
  },
  {
    name: "Utószezon",
    from: "09-01",
    to: "10-31",
    extra_price: 0,
    min_nights: 2,
  },
  {
    name: "Szezonon kínül",
    from: "11-01",
    to: "12-31",
    extra_price: 0,
    min_nights: 2,
  },
];

const room_prices = [
  {
    name: "Maui apartman",
    capacity: 2,
    price: 22000,
  },
  {
    name: "Sir David apartman",
    capacity: 2,
    price: 22000,
  },
  {
    name: "Herr Mayer apartman",
    capacity: 4,
    price: 22000,
    extra_guests: 5000,
  },
  {
    name: "Deluxe sátor",
    capacity: 4,
    price: 15000,
    extra_guests: 5000,
  },
];

export default {
  name: "Messages",
  data() {
    return {
      seasons: seasons,
      thisSeason: {
        name: undefined,
        extra_price: undefined,
        min_nights: undefined,
      },
      night_number: undefined,
      rooms: undefined,
      adults_number: 1,
      final_price: 0,
    };
  },
  created() {},
  props: {
    arrival: String,
    selected_dates: undefined,
    selected_rooms: undefined,
    adults: undefined,
  },
  watch: {
    arrival: function (arrival) {
      this.getSeason(arrival);
    },
    selected_dates: function (selected_dates) {
      this.night_number = selected_dates.length - 1;
    },
    selected_rooms: function (selected_rooms) {
      this.rooms = selected_rooms;
      this.calculatePrice(this.rooms, this.adults_number);
    },
    adults: function (adults) {
      this.adults_number = parseInt(adults);
      this.calculatePrice(this.rooms, this.adults_number);
    },
  },
  methods: {
    getSeason(arrival) {
      var year = new Date().getFullYear();
      var today = new Date(arrival);
      this.seasons.forEach((season) => {
        var season_start = year + "-" + season["from"];
        var season_end = year + "-" + season["to"];
        season_start = new Date(season_start);
        season_end = new Date(season_end);
        if (today >= season_start && today <= season_end) {
          this.thisSeason.name = season["name"];
          this.thisSeason.price = season["price"];
          this.thisSeason.min_nights = season["min_nights"];
        }
      });
    },
    calculatePrice(rooms, adults) {
      var temp = [];
      room_prices.forEach((price) => {
        if (rooms.includes(price["name"])) {
          while (adults > 0 && price["capacity" > 0]) {
            temp.push(adults * price["price"]);
            adults = adults - 1;
            console.log(price["capacity"]);
            price["capacity"] = price["capacity"] - 1;
          }
        }
      });
      console.log(temp);
    },
  },
};
</script>

