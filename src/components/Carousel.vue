<template>
  <div id="carousel">
    <div :id="currId" class="carousel slide">
      <div class="carousel-inner">
        <div
          :class="['carousel-item', { active: i === 1 }]"
          v-for="(video, i) in videos"
          :key="i"
        >
          <video
            :src="video"
            class="video-slide d-block w-100"
            :alt="video"
            controls
          ></video>
        </div>
      </div>
      <button
        class="carousel-control-prev"
        type="button"
        :data-bs-target="'#' + currId"
        data-bs-slide="prev"
      >
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Previous</span>
      </button>
      <button
        class="carousel-control-next"
        type="button"
         :data-bs-target="'#' + currId"
        data-bs-slide="next"
      >
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="visually-hidden">Next</span>
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: "carousel",
  props: {
    videos: {
      type: Array,
      required: true,
    },
    currId: {
      type: String,
      required: true,
    },
  },
  components: {},
  data() {
    return {};
  },
  methods: {},
};
</script>

<style scoped>
.carousel {
  width: 40rem;
}
</style>
