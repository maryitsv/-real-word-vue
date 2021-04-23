<template>
  <router-link :to="{name:'EventDetails', params:{id: event.id}}">
    <div class="event-card">
      <span>@{{ event.time }} on {{ event.date }}</span>
      <h4>{{ event.title }}</h4>
    </div>
  </router-link>
</template>

<script>
export default {
  name: "EventCard",
  props: {
    event: Object,
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
a{
  text-decoration: none;
  color: gray;
}

.event-card{
  padding: 20px;
  margin-top: 12px;
  box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
  width: 50%;
}

</style>
