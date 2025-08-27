<template>
  <div id="about">
    <button class="aboutBtn" @click="openAbout">i</button>
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
.aboutBtn {
  position: absolute;
  border: none;
  color: #F4F9E1;
  font-size: 1.6rem;
  transition: background-color 0.3s ease;
  background-color: #0E5648;
  border-radius: 150px;
  width: 2.5rem;
  height: 2.5rem;
  cursor: pointer;
  left: 5rem;
  top: 1.5rem;
  font-family: "carmela";
}

.aboutBtn:hover {
  background-color: #1b6b5b;
}
.div-about {
  position: absolute;
  width: 12rem;
  left: 9rem;
  top: 2rem;
  font-family: "rubik";
  background: #F4F9E1;
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
  background-color: #d3dab7;
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

@font-face {
  font-family: aharoni;
  src: url("/src/assets/fonts/._aharoniclm-bold-webfont.ttf");
}

@font-face {
  font-family: carmela;
  src: url("/src/assets/fonts/carmela.ttf");
}
</style>
