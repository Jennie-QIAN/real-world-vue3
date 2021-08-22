<template>
  <!-- 
  bind to an object where we specify the 'name' of the route where we want it to route to  
  this is a more scalable solution (ex, imagine the path needs to be changed) 
  -->
  <router-link :to="{ name: 'EventDetails', params: { id: event.id } }">
    <div class="event-card">
      <span>@ {{ event.location }} on {{ event.date }}</span>
      <h4>{{ event.title }}</h4>
      <!-- if we want we can access the params.id with the following expression -->
      <span>Event #{{ $route.params.id }}</span>
    </div>
  </router-link>
</template>

<script>
export default {
  name: 'EventCard',
  props: {
    event: {
      type: Object,
      required: true,
    },
  },
}
</script>

<style scoped></style>
