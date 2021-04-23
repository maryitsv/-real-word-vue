<template>
  <div class="events">
    <EventCard  v-for="event in events" :key=event.id :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from "@/components/EventCard.vue";
import EventService from '@/services/EventService';

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
    EventService.getEvents().then(
      response => {
        console.log("s", response);
        this.events = response.data;
      }
    ).catch(
      error => {
        console.log("s", error);
      }
    );

  }
};
</script>
