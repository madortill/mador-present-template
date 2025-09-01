<template>
  <div id="videos">
    <div class="carousel">
      <carousel :videos="collection1Videos" :currId="'gsharim'"></carousel>
      <p class="carousel-text">מארז סרטונים - 1 </p>
    </div>
    <div class="carousel">
      <carousel :videos="collection2Videos" :currId="'kabatim'"></carousel>
      <p class="carousel-text">מארז סרטונים - 2</p>
    </div>
    <div v-for="(video, i) in moreVideos" :key="i">
      <video  :src="video.src" class="video" controls></video>
      <p class="video-text">{{ video.text }}</p>
    </div>
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
      collection1Videos: [
        "",
        "",
        ""
      ],
      collection2Videos: [
        "",
        "",
        ""
      ],
      moreVideos: [
        {src: "", text: ''},
        {src: "", text: ''}
      ]
    };
  },
  methods: {},
};
</script>

<style scoped>
.carousel-text {
  color: #EDFAFF;
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
  margin: 0rem 1rem;
  width: 40rem;
}

.video-text {
  color: #EDFAFF;
  font-family: "carmela";
  font-size: 1.5rem;
}
</style>
