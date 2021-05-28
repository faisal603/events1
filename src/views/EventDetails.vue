<template>
  <div v-if="event">
    <span>
      @ <b>{{ event.time }}</b> on {{ event.date }}
    </span>
    <h3>{{ event.title }}</h3>
    <p>{{ event.description }}</p>
  </div>
</template>

<script>
import EventService from "@/services/EventService.js";
export default {
props:['id'],
  data() {
    return {
      event: null,
    };
  },
  created() {
    EventService.getEvent(this.id).then((response) => {
      this.event = response.data;
    });
  },
};
</script>

<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
</style>
