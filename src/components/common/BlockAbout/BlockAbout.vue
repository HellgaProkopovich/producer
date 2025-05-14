<template>
  <!-- <BaseContainer theme="dark"> -->
  <BaseContainer :theme="containerTheme">
    <div class="blockabout_container">
      <div class="blockabout_textsection">
        <div class="blockabout_text">
          <!-- <BaseTitlesContainer title="Обо мне" subtitle="Уникален не я, а мой опыт" class="blockabout_subtitle" /> -->
          <BaseTitlesContainer title="Обо мне" subtitle="Уникален не я, |а мой опыт" class="blockabout_subtitle" />
          <p class="text-l text-black">
            Годы в Премьер и Высшей Лиге КВН, сценаристика, реклама, документалистика, работа с художниками, фестивалями, диджеинг, йога — и параллельно проекты для бизнеса, государства, стартапов и IT.
            <br><br>
            Этот опыт дал мне сеть нестандартно мыслящих людей, чьи таланты я привлекаю под идею и задачу.
          </p>
          <BaseButton href="" size="small" class="blockabout_btn">Портфолио</BaseButton>
        </div>
      </div>
      <div class="bloclabout_imgsection">
        <img class="blockabout_img" src="../../../assets/img/img_blockabout.png" alt="img_blockabout">
      </div>
    </div>
  </BaseContainer>
</template>

<script>
export default {
  name: 'BlockAbout',

  data() {
    return {
      isMobile: false
    }
  },
  computed: {
    containerTheme() {
      return this.isMobile ? 'light' : 'dark'
    }
  },
  mounted() {
    this.checkScreen()
    window.addEventListener('resize', this.checkScreen)
  },
  beforeUnmount() {
    window.removeEventListener('resize', this.checkScreen)
  },
  methods: {
    checkScreen() {
      this.isMobile = window.innerWidth <= 768
    }
  }
}
</script>

<style>
.blockabout_container {
  display: flex;
  flex-direction: row;
  margin-top: 0;
  position: relative;
  z-index: 0;

  @media screen and (max-width: $sizeMobile) {
    flex-direction: column;
  }
}

.blockabout_textsection {
  background-color: var(--color-gray-30);
  position: relative;
  width: 100vw;
  padding-top: 40px;
}
.blockabout_textsection::before {
  background-color: var(--color-gray-30);
  content: "";
  position: absolute;
  top: 0;
  right: 0;
  width: 100vw;
  height: 100%;
  z-index: -1;

  @media screen and (max-width: $sizeMobile) {
    bottom: 0;
    width: 150%;
  }
}

.blockabout_subtitle {
  color: var(--color-black);
}

.blockabout_text {
  width: 60%; /* 522px; */

  @media screen and (max-width: $sizeMobile) {
    width: 95%;
  }
}

.blockabout_btn {
  width: 197px;
  margin-top: 75px;
  margin-bottom: 75px;

  @media screen and (max-width: $sizeMobile) {
    width: 194px;
    margin-top: 40px;
    margin-bottom: 20px;
  }
}

.bloclabout_imgsection {
  background-color: var(--color-black);
  min-width: 430px;

  @media screen and (max-width: $sizeMobile) {
    background-color: var(--color-white);
    position: relative;
    width: 100vw;
    min-width: unset;
  }
}

.blockabout_img {
  position: absolute;
  right: 0;
  max-width: 738px;
  width: 170%;
  margin-top: 40px;

  @media screen and (max-width: $sizeMobile) {
    position: relative;
    width: 95%;
    margin-top: 10px;
  }
}
</style>
