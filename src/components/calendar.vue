<template>
  <div class="main_div">
    <div class="calendar_div" id="calendar">
      <FullCalendar :options="calendarOptions" />
    </div>
  </div>
</template>

<script>
import FullCalendar from "@fullcalendar/vue";
import dayGridPlugin from "@fullcalendar/daygrid";
import interactionPlugin from "@fullcalendar/interaction";
import googleCalendarPlugin from "@fullcalendar/google-calendar";

const calendars = [
  {
    googleCalendarId: "ulaqgt06tkftv7tjot9vfttelo@group.calendar.google.com",
    className: "event sirdavid",
    color: "orange",
  },
  {
    googleCalendarId: "2g8f12h9tp0gnh7rf1np777qe0@group.calendar.google.com",
    className: "event maui",
    color: "red",
  },
  {
    googleCalendarId: "loj1rimcisq8746gkhptl0tnkg@group.calendar.google.com",
    className: "event herrmayer",
    color: "blue",
  },
  {
    googleCalendarId: "2ub5ill5qlotf2tgcj0l3srbls@group.calendar.google.com",
    className: "event sator",
    color: "green",
  },
];

export default {
  components: {
    FullCalendar, // make the <FullCalendar> tag available
  },
  data() {
    return {
      date_start: "",
      date_end: "",
      selected_dates: [],
      calendarOptions: {
        plugins: [dayGridPlugin, interactionPlugin, googleCalendarPlugin],
        googleCalendarApiKey: "AIzaSyAoSeDNyvh9JVNSoZpuoPtt-afjqUKsjQU",
        locale: "hu",
        height: "auto",
        firstDay: 1,
        initialView: "dayGridMonth",
        fixedWeekCount: false,
        dateClick: this.handleDateClick,
        eventOverlap: true,
        eventSources: calendars,
        eventsSet: this.handleChange,
      },
    };
  },
  created() {},
  props: {
    room: String,
    hide: Boolean,
  },
  watch: {
    hide: function () {
      if (this.hide == false) {
        this.showEvent(this.room);
      } else {
        this.hideEvent(this.room);
      }
    },
    room: function () {
      if (this.hide == false) {
        this.showEvent(this.room);
      } else {
        this.hideEvent(this.room);
      }
    },
  },
  methods: {
    showEvent(value) {
      var elements = document.getElementsByClassName(value);
      elements.forEach((element) => {
        element.classList.remove("hidden");
      });
    },
    hideEvent(value) {
      var elements = document.getElementsByClassName(value);
      elements.forEach((element) => {
        element.classList.add("hidden");
      });
    },
    handleDateClick: function (arg) {
      if (arg.dayEl.classList.contains("fc-day-future")) {
        console.log(arg);
        if (this.date_start === "") {
          arg.dayEl.classList.add("selected_dates");
          this.date_start = new Date(arg.dateStr);
          document.getElementById("start_input").value = arg.dateStr;
          this.$emit("get_arrival_date", arg.dateStr);
          return this.date_start;
        } else {
          this.date_end = new Date(arg.dateStr);
          document.getElementById("end_input").value = arg.dateStr;
          this.$emit("get_leave_date", arg.dateStr);
          if (this.date_end < this.date_start) {
            this.clearSelectedDates();
            arg.dayEl.classList.add("selected_dates");
            this.date_start = this.date_end;
            this.date_end = "";
            document.getElementById("start_input").value = this.date_start;
            this.$emit("get_arrival_date", this.date_start);
            return this.date_start, this.date_end;
          } else if (this.date_end.getTime() === this.date_start.getTime()) {
            this.date_start = "";
            this.date_end = "";
            this.clearSelectedDates();
            return this.date_start, this.date_end;
          } else {
            this.clearSelectedDates();
            this.findSelectedDates(this.date_start, this.date_end);
          }
        }
      }
    },
    clearSelectedDates() {
      var elements = document.getElementsByClassName("fc-day-future");
      elements.forEach((element) => {
        if (element.classList.contains("selected_dates"));
        element.classList.remove("selected_dates");
      });
      this.selected_dates = [];
    },
    findSelectedDates(start, end) {
      this.selected_dates = [];
      while (start <= end) {
        var d = start.getDate();
        if (d < 10) {
          d = "0" + d;
        }
        var m = start.getMonth() + 1;
        if (m < 10) {
          m = "0" + m;
        }
        var y = start.getFullYear();
        this.selected_dates.push(y + "-" + m + "-" + d);
        start.setDate(start.getDate() + 1);
      }
      document.getElementsByClassName("fc-day-future").forEach((date) => {
        this.selected_dates.forEach((selected_date) => {
          if (date.dataset.date === selected_date) {
            date.classList.add("selected_dates");
          }
        });
      });
      this.date_start = new Date(this.selected_dates[0]);
      return this.selected_dates;
    },
    handleChange: function () {
      document.getElementsByClassName("fc-day-future").forEach((date) => {
        this.selected_dates.forEach((selected_date) => {
          if (date.dataset.date === selected_date) {
            date.classList.add("selected_dates");
          }
        });
      });
    },
  },
};
</script>


<style>
.calendar_div {
  padding: 15px;
  box-shadow: 0 4px 8px 0 rgba(0, 0, 0, 0.2), 0 6px 20px 0 rgba(0, 0, 0, 0.19);
}

.event {
  color: white;
  pointer-events: none;
  cursor: default;
}

.fc-event-start {
  margin-left: 30px !important;
}
.fc-event-end {
  margin-right: -20px !important;
}

.fc-day-future:hover {
  background-color: rgba(189, 189, 188, 0.13);
  cursor: pointer;
}

.fc-day-past {
  background-color: rgba(189, 188, 188, 0.13);
}

.selected_dates {
  background-color: rgb(123, 182, 250);
}

.selected_dates:hover {
  background-color: rgba(90, 133, 182, 0.678);
}
</style>
