<template>
  <div id="app">
    <Timeline :events="eventsData" />
  </div>
</template>

<script>
import Timeline from './components/Timeline.vue';

export default {
  name: 'App',
  components: {
    Timeline,
  },
  data() {
    return {
      eventsData: [
        {
          title: 'Event 1',
          date: '2022-01-15',
          description: 'Description for Event 1',
        },
        {
          title: 'Event 2',
          date: '2022-02-20',
          description: 'Description for Event 2',
        },
        {
          title: 'Event 3',
          date: '2022-03-10',
          description: 'Description for Event 3',
        },
        // Add more events as needed
      ],
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
