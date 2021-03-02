<template>
  <div>
    <p class="hiba" v-if="thisSeason.min_nights > 1">
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
    price: "15.000,-Ft",
    min_nights: 1,
  },
  {
    name: "Előszezon",
    from: "04-01",
    to: "07-14",
    price: "20.000,-Ft",
    min_nights: 2,
  },
  {
    name: "Főszezon",
    from: "07-15",
    to: "08-31",
    price: "24.000,-Ft",
    min_nights: 2,
  },
  {
    name: "Utószezon",
    from: "09-01",
    to: "10-31",
    price: "20.000,-Ft",
    min_nights: 2,
  },
  {
    name: "Szezonon kínül",
    from: "11-01",
    to: "12-31",
    price: "15.000,-Ft",
    min_nights: 1,
  },
];

export default {
  name: "Hiba",
  data() {
    return {
      seasons: seasons,
      thisSeason: {
        name: "Szezonon kívül",
        price: "15.000,-Ft",
        min_nights: 1,
      },
    };
  },
  created() {},
  props: {
    arrival: String,
    leave: String,
  },
  watch: {
    arrival: function (arrival) {
      this.getSeason(arrival);
    },
    leave: {},
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
  },
};
</script>