<template>
  <div>
    <div class="row">
      <div class="col-sm-2">
        Zurück
      </div>
      <div class="col-sm-10">
          <section id="calendar-records">
            <div v-for="(event_item, eventid, eventindex) in eventliste" :key="eventindex">
              <div class="row event-container">
                <div class="col-sm-9">
                  <div class="row">
                    <div class="col-sm-12 room-display">
                      <p>{{ eventitem.room }}</p>
                    </div>
                  </div>
                  <div class="row">
                    <div class="col-sm-2 start_time_display">
                      <h5>{{ eventitem.start_time }}</h5>
                    </div>
                    <div class="col-sm-4 title_display">
                      <h5>{{ eventitem.title }}</h5>
                    </div>
                  </div>
                </div>
                <!-- <div class="col-sm-3">
                  <p class="event-star" v-bind:id="eventid" @click="favorite_event(eventid)">{{eventstar}}</p>
                </div> -->
              </div>
          </div>
        </section>
      </div>
    </div>
    <div class="row">
      <h3>Beschreibung:</h3>
    </div>
    <div class="row" v-for="(value, eventid, eventindex) in eventliste" :key="eventindex">
      {{ eventitem.description }}
    </div>
    <div class="row"><h3>Datum:</h3></div>
    <div class="row" v-for="(eventitem, eventid, eventindex) in eventliste" :key="eventindex">
      {{ eventitem.starttime }} - {{ eventitem.endtime }} <br>
      {{ eventitem.date }}
    </div>
    <br><br>
  </div>
</template>

<script>

export default{
  prop: {
    eventitem: Object,
    eventid: String,
    eventindex: Number,
    eventstar: String,
    eventliste: Object,
    
  }
}

</script>
