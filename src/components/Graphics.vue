<template>
  <div id="graphics">
    <video
      v-for="(video, i) in videoData"
      :key="i"
      :src="video"
      class="video"
      controls
      autoplay
      muted
    ></video>
    <img
      v-for="(graphic, i) in data"
      :key="i"
      :src="graphic"
      :alt="'graphic'"
      class="graphic"
    />
  </div>
</template>

<script>
export default {
  name: "graphics",
  components: {},
  data() {
    return {
      data: [
        "",
      ],
      videoData: [
        "",
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
#graphics {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-content: center;
}

.graphic {
  max-width: 47rem;
  max-height: 20rem;
  margin: 0.5rem 0.5rem;
}

.video {
  margin: 1rem 1rem;
  height: 20rem;
}
</style>
