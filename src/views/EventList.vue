<template>
  <h1>Events for Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from '@/components/EventCard.vue'
import EventService from '../services/EventService'

export default {
  name: 'EventList',
  data() {
    return {
      events: null
    }
  },
  created() {
    EventService.getEvents()
      .then(res => {
        this.events = res.data
      })
      .catch(err => {
        console.log(err)
      })
  },
  components: {
    EventCard
  }
}
</script>
<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
