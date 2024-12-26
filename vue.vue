<template>
  <div class="clock">
    {{ time }}
  </div>
</template>

<script>
export default {
  data() {
    return {
      time: ''
    };
  },
  methods: {
    updateTime() {
      const now = new Date();
      const hours = String(now.getHours()).padStart(2, '0');
      const minutes = String(now.getMinutes()).padStart(2, '0');
      const seconds = String(now.getSeconds()).padStart(2, '0');

      this.time = `${hours}:${minutes}:${seconds}`;
    }
  },
  created() {
    // Set initial time
    this.updateTime();
    // Update the time every second
    setInterval(this.updateTime, 1000);
  }
};
</script>

<style scoped>
.clock {
  font-size: 48px;
  font-weight: bold;
  padding: 20px;
  background-color: #333;
  color: white;
  border-radius: 10px;
  text-align: center;
}
</style>
