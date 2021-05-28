<template>
  <div class="events" >
    <eventer v-for="event in events" :key="event.id" :event="event" />
  </div>
</template>

<script>
// @ is an alias to /src
import eventer from "@/components/eventer.vue";
import EventService from '@/services/EventService.js'

export default {
  data() {
    return {
      events: null,
    };
  },
  created() {
    EventService.getEvents().then((response) => {
      this.events = response.data;
    });
  },
  name: "EventList",
  components: {
    eventer,
  },
};
</script>

<style scoped>
.events {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.events li {
  list-style-type: none;
}
</style>
