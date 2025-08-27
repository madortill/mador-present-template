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
    </div>
  </div>
</template>

<script>
export default {
  name: "mop",
  components: {},
  data() {
    return {
      mopData: [
        { id: "", title: "", text: '', src: "" }
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
  align-items: center;
  justify-content: center;
}

.lomda-card {
  height: 30rem;
  width: 20rem;
  background-color: #f4f9e1;
  border: 5px solid #d2e4b0;
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
}

.lomda-title {
  margin-top: 0rem;
  font-size: 2rem;
  margin-bottom: -0.5rem;
}

.lomda-text {
  margin-top: 0rem;
  font-size: 1.1rem;
}
</style>
