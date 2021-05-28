<template>
<router-link :to="{name: 'EventDetails', params:{id: event.id}}">
  <div class="event-card" id="desi">
    <span>
      @ <b>{{ event.time }}</b> on {{ event.date }}
    </span>
    <h3>{{ event.title }}</h3>
  </div>
</router-link>
</template>

<script>
export default {
  name: "eventer",
  props: {
    event: {
      type: Object,
      required: true,
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.event-card {
  padding: 20px;
  width: 250px;
  cursor: pointer;
  border: 1px solid #39495c;
  margin-bottom: 18px;
}
#desi a{
  text-decoration: double;
  color:black;

}
.event-card:hover {
  transform: scale(1.01);
  box-shadow: 0 3px 12px 0 rgba(0, 0, 0, 0.2);
}
</style>
