<template>
  <div class="events">
    <EventCard  v-for="event in events" :key=event.id :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue";
import axios from 'axios';

export default {
  name: "EventList",
  components: {
    EventCard,
  },
  data() {
    return {
      events: null
    }
  },
  created(){
    axios.get(
      'db.json'
    ).then(
      response => {
        console.log("s", response);
      }
    ).catch(
      error => {
        console.log("s", error);
      }
    );

  }
};
</script>
