<template>
  <div id="social">
    <video v-for="(video, i) in socialVideos" :key="i" :src="video" class="tiktok" controls autoplay muted></video>
  </div>
</template>

<script>
export default {
  name: "social",
  components: {},
  data() {
    return {
        socialVideos: [
            ""
        ]
    };
  },
  methods: {},
};
</script>

<style scoped>
#social {
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.tiktok {
    margin: 0rem 1rem;
    max-height: 30rem;
}
</style>
