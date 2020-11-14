<template>
  <h1>Events for Good</h1>
  <div class="events">
    <EventCard v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import EventCard from '@/components/EventCard.vue'

export default {
  name: 'EventList',
  data() {
    return {
      events: [
        {
          id: 222,
          category: 'test event',
          title: 'test event title',
          description: 'event description test',
          location: 'Castelo Branco',
          date: '02/02/2020',
          time: '12:00',
          petsAllowed: true,
          organizer: 'John Doe'
        },
        {
          id: 223,
          category: 'test event 2',
          title: 'test event title 2',
          description: 'event description test',
          location: 'Amsterdam',
          date: '02/02/2020',
          time: '12:00',
          petsAllowed: true,
          organizer: 'John Doe'
        }
      ]
    }
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
