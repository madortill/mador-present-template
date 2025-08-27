<template>
  <div id="images">
    <div class="image-card" v-for="(img, i) in data" :key="i">
      <img :src="img.src" :alt="img.alt" class="image-png" />
      <p class="img-text">{{ img.text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "images",
  components: {},
  data() {
    return {
      data: [
        {
          text: '',
          src: "",
          alt: "",
        }
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
#images {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  align-content: center;
}

.image-card {
    margin: 0rem 0.3rem;
    text-align: center;
    align-content: center;
}

.image-png {
  max-height: 30rem;
  max-width: 25rem;
}

.img-text {
    color: #F4F9E1;
    font-family: "carmela";
}
</style>
