<template>
  <div id="fields">
    <div
      v-for="(btn, index) in fieldData"
      :key="index"
      :id="btn.id"
      class="field-btn"
    >
      <p class="field-text" :id="btn.id">{{ btn.title }}</p>
      <img :src="btn.src" :alt="btn.id" class="field-img" :id="btn.id" />
    </div>
  </div>
</template>

<script>
export default {
  name: "fields",
  components: {},
  data() {
    return {
      fieldData: [
        { id: "social", title: "סושיאל", src: "./assets/general/social.svg" },
        { id: "mop", title: "לומדות", src: "./assets/general/mop.svg" },
        {
          id: "graphics",
          title: "גרפיקה",
          src: "./assets/general/graphics.svg",
        },
        { id: "images", title: "תמונות", src: "./assets/general/images.svg" },
        {
          id: "videos",
          title: "סרטונים",
          src: "./assets/general/videos.svg",
        },
      ],
    };
  },
  methods: {},
};
</script>

<style scoped>
#fields {
  display: grid;
  grid-template-columns: repeat(3, 1fr); 
  gap: 4rem 6rem;
  justify-items: center;
  align-items: center;
  max-width: 800px;
  margin: 0 auto;
}
.field-btn {
  display: flex;
  text-align: center;
  background-color: #d2e4b0;
  border-radius: 20px;
  justify-content: center;
  width: 14rem;
  height: 14rem;
  flex-direction: column;
  align-content: center;
  align-items: center;
  border: 5px solid #f4f9e1;
  cursor: pointer;
  transition: 0.3s;
}

.field-btn:hover {
  background-color: #f4f9e1;
  border: 5px solid #d2e4b0;
}

.field-btn:active {
  background-color: #acbe88;
}

.field-img {
  height: 7.5rem;
}

.field-text {
  margin: 0rem;
  font-size: 2.5rem;
}

.field-btn:nth-child(n + 4) {
  transform: translateX(-10rem); /* חצי מהרוחב של עמודה + חצי gap */
}
</style>
