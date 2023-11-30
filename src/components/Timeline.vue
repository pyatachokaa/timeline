<template>
  <div>
    <ul class="timeline">
      <li v-for="event in sortedEvents" :key="event.title" class="timeline-item">
        <div class="event-header">
          <h3 class="event-title">{{ event.title }}</h3>
          <span class="event-date">{{ event.date }}</span>
        </div>
        <div class="event-description">{{ event.description }}</div>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'TimelineComponent',
  props: {
    events: {
      type: Array,
      required: true,
    },
  },
  computed: {
    sortedEvents() {
      const eventsCopy = Array.from(this.events); 
      const sorted = eventsCopy.sort((a, b) => new Date(a.date) - new Date(b.date));
      return sorted;
    },
  },
}
</script>

<style>
.timeline {
  background-color: purple;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
}

.timeline-item {
  position: relative;
  display: flex;
  align-items: center;
  margin-bottom: 20px;
}

.timeline-title {
  cursor: pointer;
  color: white;
  text-decoration: underline;
  margin-right: 10px;
}

.timeline-details {
  position: absolute;
  left: calc(100% + 30px);
  top: 50%;
  transform: translateY(-50%);
  background-color: white;
  padding: 10px;
  display: none;
  flex-direction: column;
}

.timeline-details p {
  margin: 0;
}

.timeline-title.active {
  text-decoration: none;
}

.timeline-title.active + .timeline-details {
  display: flex;
}
</style>