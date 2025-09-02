<template>
  <div id="about">
    <div class="btn">
      <button class="aboutBtn" @click="openAbout">i</button>
      <p class="text">אודות</p>
    </div>
    <Transition name="fade">
      <div v-show="showAbout" class="div-about">
        <h4 class="list-text-about">מפתחת ראשית:</h4>
        <p class="list-text-about">טוראי גילי נחום</p>
        <h4 class="list-text-about">עיצוב האתר:</h4>
        <p class="list-text-about">טוראי גילי נחום</p>
        <h4 class="list-text-about">רמ"ד טי"ל:</h4>
        <p class="list-text-about">רס"מ עדן בן חמו</p>
        <h4 class="list-text-about">גרסה:</h4>
        <p class="list-text-about">אוגוסט 2025</p>
      </div>
    </Transition>
  </div>
</template>

<script>
export default {
  name: "about",
  components: {},
  data() {
    return {
      showAbout: false,
      clickBtn: 0,
    };
  },
  methods: {
    openAbout() {
      if (this.clickBtn % 2 === 0) {
        this.showAbout = true;
      } else {
        this.showAbout = false;
      }
      this.clickBtn++;
    },
  },
};
</script>

<style scoped>
.btn {
  position: absolute;
  left: 1.5rem;
  bottom: 0rem;
  text-align: center;
}
.aboutBtn {
  border: none;
  color: #0e3656;
  font-size: 1.9rem;
  transition: background-color 0.3s ease;
  background-color: #edfaff;
  border-radius: 150px;
  width: 3rem;
  height: 3rem;
  cursor: pointer;
  font-family: "carmela";
}

.aboutBtn:hover {
  background-color: #a6c7d4;
}
.div-about {
  position: absolute;
  width: 12rem;
  left: 6rem;
  bottom: 2rem;
  font-family: "rubik";
  background: #EDFAFF;
  border-radius: 1rem;
  box-shadow: 0 15px 20px -20px rgba(0, 0, 0, 0.4);
  text-align: center;
  padding: 1rem;
  z-index: 3;
}

.list-text-about {
  transition: background-color 0.5s ease;
  margin: 5%;
}
.list-text-about:hover {
  background-color: #bddae6;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.5s ease;
}
.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
.fade-enter-to,
.fade-leave-from {
  opacity: 1;
}

.text {
  font-size: 0.9rem;
  color: #edfaff;
}

@font-face {
  font-family: aharoni;
  src: url("/src/assets/fonts/._aharoniclm-bold-webfont.ttf");
}

@font-face {
  font-family: carmela;
  src: url("/src/assets/fonts/carmela.ttf");
}
</style>
