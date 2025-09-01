<template>
  <div id="mop">
    <div
      v-for="(lomda, index) in mopData"
      :key="index"
      :id="lomda.id"
      class="lomda-card"
    >
      <img :src="lomda.src" :alt="lomda.id" class="lomda-img" :id="lomda.id" />
      <p class="lomda-title">{{ lomda.title }}</p>
      <p class="lomda-text">{{ lomda.text }}</p>
      <img :src="lomda.qr" :alt="lomda.id" class="lomda-qr" :id="lomda.id" />
    </div>
  </div>
</template>

<script>
export default {
  name: "mop",
  components: {
  },
  data() {
    return {
      mopData: [
        { id: "", title: "", text: '', src: "", qr: "" }
      ],
    };
  },
  methods: {
  },
};
</script>

<style scoped>
#mop {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}

.lomda-card {
  height: 30rem;
  width: 20rem;
  background-color: #EDFAFF;
  border: 5px solid #B3D8F3;
  border-radius: 20px;
  text-align: center;
  margin: 1rem;
  font-family: "carmela";
  padding: 0.2rem;
}

.lomda-img {
  margin-top: 0.3rem;
  max-width: 18rem;
  border-radius: 20px;
  margin-bottom: 0rem;
  max-height: 18rem;
}

.lomda-title {
  margin-top: 0rem;
  font-size: 1.8rem;
  margin-bottom: -0.5rem;
}

.lomda-text {
  margin-top: 0rem;
  margin-bottom: 0rem;
  font-size: 1rem;
}

.lomda-qr {
  margin-top: 0rem;
  height: 5rem;
}
</style>
