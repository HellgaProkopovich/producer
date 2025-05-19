<template>
  <BaseContainer class="block-services">
    <div class="block-services__container">
      <BaseTitlesContainer
        align="right"
        title="Услуги"
        subtitle="Основные направления"
        class="block-services__title"
      >
      </BaseTitlesContainer>

      <div class="block-services__services-section">
        <div class="block-services__service-item">
          <svg class="block-services__service-img">
            <use xlink:href="#icon-pen" />
          </svg>
          <p class="block-services__service-title text-s text-w700">Креативные концепции</p>
          <p class="block-services__service-description text-3xs">
            Глубоко вникаю в суть задачи и создаю текст, сценарии, концепции и план
          </p>
        </div>

        <div class="block-services__service-item">
          <svg class="block-services__service-img">
            <use xlink:href="#icon-star" />
          </svg>
          <p class="block-services__service-title text-s text-w700">Продюсирование</p>
          <p class="block-services__service-description text-3xs">
            Организую съёмку под ключ: команда, процессы, результат и контроль
          </p>
        </div>

        <div class="block-services__service-item">
          <svg class="block-services__service-img">
            <use xlink:href="#icon-smile" />
          </svg>
          <p class="block-services__service-title text-s text-w700">Ивенты</p>
          <p class="block-services__service-description text-3xs">
            Креативная и техническая поддержка событий: от идеи до атмосферы
          </p>
        </div>

        <div class="block-services__service-item">
          <svg class="block-services__service-img">
            <use xlink:href="#icon-clock" />
          </svg>
          <p class="block-services__service-title text-s text-w700">Мозговые штурмы</p>
          <p class="block-services__service-description text-3xs">
            Направляю команды в процессе поиска решений и креатива
          </p>
        </div>
      </div>

      <div class="block-services__text-section text-l">
        <p>Стоимость высчитывается после исследования задачи.</p>
        <p>Каждый проект начинается с разговора и понимания. Только потом — цифры.</p>
      </div>

      <BaseButton href="" size="small" class="block-services__btn">Связаться</BaseButton>
    </div>
  </BaseContainer>
</template>

<script>
export default {
  name: 'block-services',
}
</script>

<style lang="postcss">
.block-services__container {
  padding-top: 92px;
  padding-bottom: 120px;

  @media screen and (max-width: $sizeMobile) {
    padding-top: 60px;
    padding-bottom: 60px;
  }
}

.block-services__title {
  margin-bottom: 80px;

  @media screen and (max-width: $sizeMobile) {
    margin-bottom: 64px;
  }
}

.block-services__services-section {
  display: flex;
  gap: 20px;
  padding-bottom: 70px;
  margin-bottom: 40px;
  border-bottom: 1px solid var(--color-primary);

  @media screen and (max-width: 900px) {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }

  @media screen and (max-width: $sizeMobile) {
    grid-template-columns: 1fr;
    gap: 40px;
    padding-bottom: 102px;
    margin-bottom: 24px;
  }
}

.block-services__service-img {
  width: 20px;
  height: 20px;
  margin-bottom: 15px;

  @media screen and (max-width: $sizeMobile) {
    margin-bottom: 12px;
  }
}

.block-services__service-title {
  margin-bottom: 24px;
}

.block-services__btn {
  max-width: 197px;
  margin-top: 40px;

  @media screen and (max-width: $sizeMobile) {
    max-width: 194px;
  }
}
</style>
