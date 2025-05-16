<template>
  <BaseContainer :theme="containerTheme">
    <div class="blockabout blockabout__container">
      <div class="blockabout__textsection">
        <div class="blockabout__text">

          <BaseTitlesContainer title="Обо мне">
            <template #subtitle>
              <span class="blockabout__subtitle titles-container_linebreak">Уникален не я, </span>
              <span class="blockabout__subtitle titles-container_linebreak">а мой опыт</span>
            </template>
          </BaseTitlesContainer>

          <p class="text-l text-black">
            Годы в Премьер и Высшей Лиге КВН, сценаристика, реклама, документалистика, работа с художниками, фестивалями, диджеинг, йога — и параллельно проекты для бизнеса, государства, стартапов и IT.
            <br><br>
            Этот опыт дал мне сеть нестандартно мыслящих людей, чьи таланты я привлекаю под идею и задачу.
          </p>
          <BaseButton href="" size="small" class="blockabout__btn">Портфолио</BaseButton>
        </div>
      </div>
      <div class="bloclabout__imgsection">
        <img class="blockabout__img" src="./assets/img_blockabout.png" alt="img about producer">
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
.blockabout {
  $sizeTablet: 1200px;
}

.blockabout__container {
  display: flex;
  position: relative;
  z-index: 0;

  @media screen and (max-width: $sizeMobile) {
    flex-direction: column;
  }
}

.blockabout__textsection {
  background-color: var(--color-gray-30);
  position: relative;
  flex: 1 1 60%;
  padding-top: 40px;

  @media screen and (max-width: $sizeMobile) {
    width: 100vw;
  }
}
.blockabout__textsection::before {
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

.blockabout__subtitle {
  color: var(--color-black);
  white-space: nowrap;
}

.blockabout__text {
  width: 60%; /* 522px; */
  max-width: 522px;
  padding-right: 40px;

  @media screen and (max-width: $sizeMobile) {
    width: 95%;
    max-width: none;
    padding-right: 10px;
  }
}

.blockabout__btn {
  width: 197px;
  margin-top: 75px;
  margin-bottom: 75px;

  @media screen and (max-width: $sizeMobile) {
    width: 194px;
    margin-top: 40px;
    margin-bottom: 20px;
  }
}

.bloclabout__imgsection {
  background-color: var(--color-black);
  /* min-width: 430px; */
  flex: 1 1 28%;
  padding-top: 40px;

  @media screen and (max-width: $sizeMobile) {
    background-color: var(--color-white);
    position: relative;
    width: 100vw;
    min-width: unset;
    padding-top: 10px;
  }
}

.blockabout__img {
  /* position: absolute;
  right: 0; */
  transform: translateX(-43%);
  max-width: 738px;
  width: 170%;

  @media screen and (max-width: $sizeMobile) {
    /* position: relative; */
    transform: none;
    width: 95%;
  }
}
</style>
