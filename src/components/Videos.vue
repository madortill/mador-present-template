<template>
  <div id="videos">
    <div class="carousel">
      <carousel :videos="gsharimVideos" :currId="'gsharim'"></carousel>
      <p class="carousel-text">קורס גשרים - בה"ד חינוך</p>
    </div>
    <div class="carousel">
      <carousel :videos="kabatimVideos" :currId="'kabatim'"></carousel>
      <p class="carousel-text">סרטוני קב"טים</p>
    </div>
    <video v-for="(video, i) in moreVideos" :key="i" :src="video" class="video" controls></video>
  </div>
</template>

<script>
import Carousel from "@/components/Carousel.vue";
export default {
  name: "videos",
  components: {
    Carousel
  },
  data() {
    return {
      gsharimVideos: [
        "",
        ""
      ],
      kabatimVideos: [
        "",
        ""
      ],
      moreVideos: [
      ""
      ]
    };
  },
  methods: {},
};
</script>

<style scoped>
.carousel-text {
  color: #F4F9E1;
  font-family: "carmela";
  font-size: 1.5rem;
}
#videos {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  text-align: center;
}

.carousel {
  margin: 0rem 1rem;
}

.video {
  margin: 1rem 1rem;
  width: 40rem;
}
</style>
