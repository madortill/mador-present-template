<template>
  <div id="app">
    <div class="header">
      <img class="til" src="/src/assets/general/til.svg" alt="til" />
      <img
        class="mifkada"
        src="/src/assets/general/mifkada.svg"
        alt="mifkada"
      />
      <img
        class="hadracha"
        src="/src/assets/general/hadracha.png"
        alt="hadracha"
      />
      <img
      v-if="page !== 'main'"
      @click="toMain"
      class="btn-back"
      src="/src/assets/general/back-btn.svg"
      alt="back-btn"
      />
      <p class="main-title">{{ title }}</p>
      <p class="second-title" v-if="page == 'main'">חציון א' 2025</p>
    </div>
    <about v-if="page == 'main'"></about>
    <div class="whole-page">
      <div class="aside" v-if="page == 'main'">
        <p class="side-title">כותרת כותרת כותרת כותרת</p>
        <p class="side-text">טקסט טקסט טקסט טקסט טקסט טקסט</p>
        <img
        class="side-img"
        src="/src/assets/general/eden.png"
        alt="sign"
      />
      </div>
      <div class="main-content">
        <p v-if="page !== 'main'" class="explain">{{ text }}</p>
        <fields v-if="page == 'main'" @click="toField"></fields>
        <mop v-if="page == 'mop'"></mop>
        <videos v-if="page == 'videos'"></videos>
        <images v-if="page == 'images'"></images>
        <social v-if="page == 'social'"></social>
        <graphics v-if="page == 'graphics'"></graphics>
      </div>
    </div>
  </div>
</template>

<script>
import About from "@/components/About.vue";
import Fields from "@/components/Fields.vue";
import Mop from "@/components/Mop.vue";
import Videos from "@/components/Videos.vue";
import Images from "@/components/Images.vue";
import Social from "@/components/Social.vue";
import Graphics from "@/components/Graphics.vue";
export default {
  name: "app",
  components: {
    About,
    Fields,
    Mop,
    Videos,
    Images,
    Social,
    Graphics,
  },

  data() {
    return {
      showAbout: false,
      title: "תוצרי מדור טיל",
      text: "",
      page: "main",
      fieldData: {
        social: {
          title: "תחום סושיאל",
          text: "צפו בסרטוני הסושיאל שהפצנו ברשתות החברתיות",
        },
        mop: {
          title: 'תחום מו"פ',
          text: "מפתחות הלומדה פיתחו והשיקו מספר לומדות לבה”דים בחציון האחרון - מוזמנים לסרוק ולראות אותן",
        },
        graphics: {
          title: "תחום גרפיקה",
          text: 'בחציון האחרון עבדנו על מספר רב של גרפיקות כאן מוצגות חלקן - ניתן להגדיל את התצוגה באמצעות (ctrl ו- "+")',
        },
        images: {
          title: "תחום וידאו - תמונות",
          text: 'הצלמים שלנו תיעדו אירועים רבים כאן מוצגות חלק מהתמונות - ניתן להגדיל את התצוגה באמצעות (ctrl ו- "+")',
        },
        videos: {
          title: "תחום וידאו",
          text: "מוזמנים לצפות בסרטונים עליהם עבדנו בחציון האחרון",
        },
      },
    };
  },
  methods: {
    toField(event) {
      this.page = event.target.id;
      this.title = this.fieldData[event.target.id].title;
      this.text = this.fieldData[event.target.id].text;
    },
    toMain() {
      this.page = "main";
      this.title = "תוצרי מדור טיל";
    },
  },
};
</script>

<style scoped>
.header {
  width: 100%;
  height: 13rem;
  background-color: #b3d8f3;
  position: fixed;
  top: 0rem;
  right: 0rem;
  z-index: 2;
  width: calc(100% - 10px);
}

html {
  font-size: calc(10px + 0.5vw);
  margin: 0;
}

#app {
  font-family: "ploni";
  height: 100vh;
  width: 100vw;
  background-color: #0e3656;
  position: absolute;
  top: 0rem;
  right: 0rem;
  color: #0e3656;
  overflow-y: scroll;
}

.til {
  position: absolute;
  height: 9rem;
  top: 1.5rem;
  right: 2rem;
  pointer-events: none;
}

.mifkada {
  position: absolute;
  height: 8rem;
  top: 0.5rem;
  left: 1rem;
}
.hadracha {
  position: absolute;
  height: 9rem;
  top: 0.5rem;
  left: 7rem;
}

.main-title {
  text-align: center;
  position: relative;
  top: 3rem;
  font-size: 5rem;
  pointer-events: none;
}

.second-title {
  text-align: center;
  position: relative;
  top: 0rem;
  font-size: 2rem;
  font-family: "carmela";
  pointer-events: none;
}

.whole-page {
  display: flex;
  justify-content: space-around;
  margin: 0rem 1rem;
}

.side-title {
  font-size: 2rem;
  color: #edfaff;
}
.side-text {
  font-family: "carmela";
  font-size: 1.4rem;
}

.side-last {
  font-family: "carmela";
  font-size: 1.4rem;
  text-align:center;
}

.side-img {
  height: 7rem;
  position: absolute;
  left: 2rem;
}

.aside {
  color: #edfaff;
  position: relative;
  top: 16rem;
  margin-left: 1rem;
  padding-left: 3rem;
  padding-bottom: 5rem;
  max-width: 50rem;
  border-left: 2px solid #b3d8f3;
}


.main-content {
  position: relative;
  top: 16rem;
}

.explain {
  position: relative;
  color: #edfaff;
  font-family: "carmela";
  text-align: center;
  font-size: 2rem;
  bottom: 1rem;
}

.btn-back {
  position: absolute;
  top: 8rem;
  left: 23rem;
  height: 3.5rem;
  width: 3.5rem;
  padding: 0.3rem;
  border-radius: 200px;
  background-color: #0e3656;
  font-size: 2.5rem;
  cursor: pointer;
  transition: all 0.3s ease;
}

.btn-back:hover {
  padding: 0.7rem;
  height: 4rem;
  width: 4rem;
}

.btn-back:active {
  background-color: #225b8a;
}

@media (max-width: 1300px) {
  .mifkada {
    height: 7rem;
  }
  .hadracha {
    height: 7rem;
    left: 6rem;
  }
}

@font-face {
  font-family: aharoni;
  src: url("/src/assets/fonts/._aharoniclm-bold-webfont.ttf");
}

@font-face {
  font-family: ploni;
  src: url("/src/assets/fonts/ploni-bold-aaa.otf");
}

@font-face {
  font-family: carmela;
  src: url("/src/assets/fonts/carmela.ttf");
}
</style>
