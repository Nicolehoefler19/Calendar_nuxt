
<template>
<div class="row">
  <div class="calendar">
      <div class="arrows-box">
        <span @click="prev" class="arrows"><i>&larr;</i></span>
        <h3 class="month">{{ month }}</h3>
        <span @click="next" class="arrows"><i>&rarr;</i></span>
      </div>
      <section id="calendar">
          <div class="day-list">
            <div class="row">
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-show="mon_val" v-for="day in current_month.slice(slice, slice + 1)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-show="tue_val" v-for="day in current_month.slice(slice + 1, slice + 2)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-show="wed_val" v-for="day in current_month.slice(slice + 2, slice + 3)" :key="day" @click="filter_events(day); change_color();">
                 <p>{{ day.slice(8, 10) }}</p>
                 <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-show="thu_val" v-for="day in current_month.slice(slice + 3, slice + 4)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }"  v-show="fri_val" v-for="day in current_month.slice(slice + 4, slice + 5)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>F</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-show="sat_val" v-for="day in current_month.slice(slice + 5, slice + 6)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-show="sun_val" v-for="day in current_month.slice(slice + 6, slice + 7)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
            </div>

            <div class="row">
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }"  v-for="day in current_month.slice(slice + 7, slice + 8)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }"  v-for="day in current_month.slice(slice + 8, slice + 9)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 9, slice + 10)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 10, slice + 11)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 11, slice + 12)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>F</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 12, slice + 13)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 13, slice + 14)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
            </div>

            <div class="row">
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 14, slice + 15)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 15, slice + 16)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 16, slice + 17)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 17, slice + 18)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 18, slice + 19)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>F</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 19, slice + 20)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 20, slice + 21)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
            </div>

            <div class="row">
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 21, slice + 22)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 22, slice + 23)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 23, slice + 24)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 24, slice + 25)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 25, slice + 26)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>F</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 26, slice + 27)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 27, slice + 28)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
            </div>

            <div class="row">
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 28, slice + 29)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 29, slice + 30)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 30, slice + 31)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 31, slice + 32)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 32, slice + 33)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>F</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 33, slice + 34)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 34, slice + 35)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
            </div>

              <div class="row">
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 35, slice + 36)" :key="day" @click="filter_events(day)">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 36, slice + 37)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 37, slice + 38)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>M</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 38, slice + 39)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>D</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 39, slice + 40)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>F</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 40, slice + 41)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
              <div class="col-ml-1">
                <div class="calendar-columm" :class="{ active: isClicked }" v-for="day in current_month.slice(slice + 41, slice + 42)" :key="day" @click="filter_events(day); change_color();">
                  <p>{{ day.slice(8, 10) }}</p>
                  <h5>S</h5>
                </div>
              </div>
            </div>
          </div>
      </section>
      <br><br>
      <section id="calendar-records">
          <div v-for="(value, name, idx) in event_list" :key="idx">
            <div class="row event-container">
              <div class="col-sm-9">
                <div class="row">
                  <div class="col-sm-12 room-display">
                    <p>{{ value.room }}</p>
                  </div>
                </div>
                <div class="row">
                  <div class="col-sm-2 start_time_display">
                    <h5>{{ value.start_time }}</h5>
                  </div>
                  <div class="col-sm-4 title_display">
                    <h5>{{ value.title }}</h5>
                  </div>
                </div>
              </div>
              <div class="col-sm-3">
                <p class="event-star" v-bind:id="name" @click="favorite_event(name)">{{star}}</p>
              </div>
            </div>
        </div>
      </section>

      <section id="organisation">
        <h2>
          Für Organisatoren
        </h2>
        <div class="row">
          <div v-for="(value, name, idx) in event_list" :key="idx">
            <div class="row event-container">
              <div class="col-sm-9">
                <div class="row">
                  <div class="col-sm-12 room-display">
                    <p>{{ value.room }}</p>
                  </div>
                </div>
                <div class="row">
                  <div class="col-sm-2 start_time_display">
                    <h5>{{ value.start_time }}</h5>
                  </div>
                  <div class="col-sm-4 title_display">
                    <h5>{{ value.title }}</h5>
                  </div>
                </div>
              </div>
              <div class="col-sm-3">
                <p class="remove" v-bind:id="name" @click="delete_event(name)">&#128465;</p>
                <p class="edit" @click="$bvModal.show('bv-modal-events-change')">&#9998;</p>
              </div>
            </div>
        </div>
        </div>
        <b-button id="show-btn" @click="$bvModal.show('bv-modal-events')">Event hinzufügen</b-button>

      </section>

      <b-modal ref="testcomp">
          <CalendarProgramm/>
      </b-modal>

      <b-button @click="showit">Test</b-button>

      <b-modal id="bv-modal-events" hide-footer>
        <template #modal-title>
          Event hinzufügen
        </template>
        <div class="d-block text-center">
            <form @submit.prevent="add_event" id="event-Modal">
                <div>
                  <label for="title" class="descriptor">Titel</label>
                  <input type="text" required id="event-title" ref="title" name="title" class="short-input">
                </div>

                <div>
                  <label for="room" class="descriptor">Raum</label>
                  <input type="text" required id="event-room" name="room" class="short-input">
                </div>

                <div>
                  <label for="date" class="descriptor">Datum</label>
                  <input type="date" required id="event-date" name="date" class="short-input">
                </div>


                <div>
                  <label for="time" class="descriptor">Uhrzeit</label>
                  <input type="time" required id="event-start" name="starttime" class="short-input">
                  -
                  <input type="time" required id="event-end" name="endtime" class="short-input">
                </div>
                <div>
                  <label for="description">Beschreibung</label>
                  <textarea name="description" id="event-description" cols="30" rows="10"></textarea>
                </div>
                <div id="event-controls">
                  <input type="submit" value="Event hinzufügen">
                </div>
            </form>
        </div>
      </b-modal>

    </div>
  </div>
</template>

<style scoped>
  *{
    font-family:Arial, Helvetica, sans-serif;
  }
</style>


<script>
  export default{
    data(){
      return {
        output: [{}],
        current_week: [],
        all_days: [],
        date: '',
        monday_events: [],
        tuesday_events: [],
        wednesday_events: [],
        thursday_events: [],
        friday_events: [],
        saturday_events: [],
        sunday_events: [],
        event_list: {},
        keys_in_dates: [],
        month: '',
        current_month: [],
        slice: 0,
        mon_val: true,
        tue_val: true,
        wed_val: true,
        thu_val: true,
        fri_val: true,
        sat_val: true,
        sun_val: true,
        all_vals: {},
        month_curr_number: 0,
        filtered_event: {},
        star: "\u2606",
        favorite_event_list: {},
        isClicked: false,
        colored: '',
        selected_date: '',
      }
    },

    props: {
      event: Object,
    },

    created(){

      //make rest of the days of the year in array
      let today = new Date();
      let end_year = new Date('December 31, 2022 23:59:59');
      let counter = 0;
      end_year.setDate(31);

      const diff_time = Math.abs(end_year - today);
      const diff_days = Math.ceil(diff_time / (1000* 60 * 60 * 24));

      do{
        let first = today.getDate() + 1;
        let day = new Date(today.setDate(first)).toISOString().slice(0, 10);
        this.all_days.push(day);
        counter++;
      }
      while(counter <= diff_days);

    },

    mounted(){
      var curr_date = new Date();
      this.month_curr_number = curr_date.getMonth();
      this.change_month(curr_date.getMonth());
      console.log(this.current_month);

    },

    methods: {
      showit(){
        this.$refs.testcomp.show();
      },
      select_day(day){
        this.selected_date = day;
        console.log(this.selected_date);
      },

      change_color(day){
          this.isClicked = !this.isClicked;
          console.log(this.isClicked);
      },

      filter_events(day){
        this.filtered_event = {};
        var res = Object.keys(this.event_list).filter(x => this.event_list[x].date.includes(day));
        for(let i = 0; i < res.length; i++){
          var content = this.event_list[res[i]];
          this.filtered_event[res[i]] = content;
          console.log(this.filtered_event);
      }

        // var res = Object.values(this.event_list).filter(idx => idx.date.includes(day));
        // var keys = Object.keys(res);
        // for(var i = 0; i < keys.length; i++){
        //   var content = res[keys[i]];
        //   this.filtered_event[i] = content;
        //   console.log(this.filtered_event);
        // }
      },

      favorite_event(id){
        var is_checked;
        var key = id;
        if(this.star == "\u2605"){
          is_checked = true;
        }

        else{
          is_checked = false;
        }

        if(is_checked == true){
          this.star = "\u2606";

          this.favorite_event_list[key] = undefined;
          //bessere Variante key zu löschen?
          delete this.favorite_event_list[key];
        }

        else if(is_checked == false){
          this.star =  "\u2605";
          this.favorite_event_list[key] = this.event_list[key];
        }

        console.log("Favorite Events:");
        console.log(this.favorite_event_list);
      },

      clear_output(){
        this.output = [{}];
      },

      clear_month_data(){
        this.month = '';
        this.current_month = [];
        this.all_vals = {};
        this.slice = 0;
        this.mon_val = true;
        this.tue_val = true;
        this.wed_val = true;
        this.thu_val = true;
        this.fri_val = true;
        this.sat_val = true;
        this.sun_val = true;
      },

      change_month(month_number){
        const months = ["Januar", "Februar", "März", "April", "Mai", "Juni", "Juli", "August", "September", "Oktober", "November", "Dezember"];
        var curr = new Date();
        curr.setMonth(month_number);
        console.log(curr);
        this.month = months[curr.getMonth()];
        const first_day = new Date();

        first_day.setMonth(month_number);

        first_day.setDate(1);

        console.log(first_day);

        while (first_day.getMonth() === curr.getMonth()) {
          this.current_month.push(new Date(first_day).toISOString().slice(0, 10));
          first_day.setDate(first_day.getDate() + 1);
        }

        //reset because of function
        first_day.setMonth(curr.getMonth());

        if(first_day.getDay() == 1){
          this.slice = 0;
        }

        else if(first_day.getDay() == 2)
        {
          this.slice = -1;
          this.mon_val = false;
        }

        else if(first_day.getDay() == 3)
        {
          this.slice = -2;
          this.mon_val = false;
          this.tue_val = false;
        }

        else if(first_day.getDay() == 4)
        {
          this.slice = -3;
          this.mon_val = false;
          this.tue_val = false;
          this.wed_val = false;
        }

        else if(first_day.getDay() == 5)
        {
          this.slice = -4;
          this.mon_val = false;
          this.tue_val = false;
          this.wed_val = false;
          this.thu_val = false;
        }

        else if(first_day.getDay() == 6)
        {
          this.slice = -5;
          this.mon_val = false;
          this.tue_val = false;
          this.wed_val = false;
          this.thu_val = false;
          this.fri_val = false;
        }

        else if(first_day.getDay() == 0)
        {
          this.slice = -6;
          this.mon_val = false;
          this.tue_val = false;
          this.wed_val = false;
          this.thu_val = false;
          this.fri_val = false;
          this.sat_val = false;
        }


      },

      add_event(submitEvent){
        this.output['title'] = submitEvent.target.elements.title.value;
        this.output['date'] = submitEvent.target.elements.date.value;
        this.output['start_time'] = submitEvent.target.elements.starttime.value;
        this.output['end_time'] = submitEvent.target.elements.endtime.value;
        this.output['descr'] = submitEvent.target.elements.description.value;
        this.output['room'] = submitEvent.target.elements.room.value;

        //assign element to list
        for(let i = 0; i < this.output.length; i++){
          this.event_list[new Date().valueOf()] = this.output;
        }

        this.clear_output();

        //console.log(Object.keys(this.event_list).filter(idx => this.event_list[idx].date.includes('2022-05-31')));
      },

      delete_event(id){
        var key = id;
        this.event_list[key] = undefined;
        this.filtered_event[key] = undefined;
        this.favorite_event_list[key] = undefined;
        //auch hier bessere Lösung?
        delete this.event_list[key];
        delete this.filtered_event[key];
        delete this.favorite_event_list[key];

        console.log(this.event_list);
      },

      prev(){
        if (this.month_curr_number <= 0) {
          this.month_curr_number = this.month_curr_number;
        }

        else{
            this.month_curr_number--;
        }

        this.clear_month_data();

        this.change_month(this.month_curr_number);
      },

      next(){

        this.month_curr_number++;

        this.clear_month_data();

        this.change_month(this.month_curr_number);
      }
    },
  }

</script>

<style scoped>

.active, .calendar-columm:hover{
  background: #00a5ce !important;
}
.calendar{
  margin: 0 auto;
  max-width: 50vw;
  background: #303030;
  color: #ffffff;
  padding: 30px;
}

.calendar-columm{
  background: #486aff;
  padding: 10px;
  font-size: 20px;
  border: 2px solid #000000;
  text-align: center;
  cursor: pointer;
}

.event-container{
  background: #486aff;
  margin: 20px 0;
  padding: 20px;
  color: #ffffff;
}

.col-ml-1{
  min-width: 90px;
  max-width: 900px;
}

.event-star, .remove, .edit{
  text-align: right;
  cursor: pointer;
  font-size: 40px;
}

.arrows{
  cursor: pointer;
  justify-content: space-between;
  display: flex;
}

.arrows-box{
  overflow: hidden;
  justify-content: space-between;
  display: flex;
}

.day-list{
  list-style: none;
}

.day-list:after{
  display: block;
  content: '';
  clear: both;
}

</style>
