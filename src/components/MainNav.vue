<script setup>
  import Button from "@/components/MainButton.vue";
</script>

<template>
  <nav class="nav">
    <ul class="list-reset nav__list">
      <li class="nav__item"><a href="#" class="nav__link">Home</a></li>
      <li class="nav__item"><a href="#" class="nav__link">About Us</a></li>
      <li class="nav__item"><a href="#" class="nav__link">Prices</a></li>
      <li class="nav__item"><a href="#" class="nav__link">Rules</a></li>
    </ul>
    <Button class="header__button" text="Get Started Now"/>
  </nav>
</template>

<style scoped lang="scss">
  .nav{
    display: flex;
    align-items: center;
    &__list{
      margin-right: 55px;
      display: flex;
      gap: 46px;
      @media (max-width: 1024px){
        flex-direction: column;
        gap: 20px;
      }
    }
    &__link{
      font-family: var(--font-family);
      font-weight: 500;
      font-size: 18px;
      line-height: 133%;
      color: var(--bismark-color);
      transition: color .2s ease;
      position: relative;
      @media (hover: hover) {
        &:hover::after {
          width: 100%; // полная ширина при наведении
        }
      }
      &:active{
        color: var(--apricot-color);
      }
      &::after {
        content: "";
        position: absolute;
        left: 0;
        bottom: -2px; // отступ от текста
        width: 0; // изначальная ширина 0 для анимации слева направо
        height: 2px; // толщина линии подчеркивания
        background-color: var(--bismark-color); // цвет подчеркивания
        transition: width 0.3s ease; // плавное увеличение ширины
      }
    }

    @media (max-width: 1024px){
      position: fixed;
      top: 0;
      right: 0;
      align-items: center;
      justify-content: center;
      flex-direction: column;
      background-color: var(--light-color);
      z-index: 9;
      width: 50vw;
      height: 100%;
      border-top-left-radius: 50%;
      border-bottom-left-radius: 50%;
      gap: 20px;
      transform: translateX(calc(100% + 6vw));
      transition: 1s cubic-bezier(.7,0,.2,1);
      will-change: transform;
    }
    @media (max-width: 768px) {
      width: 100vw;
    }
    &.active-nav{
      border-radius: 0;
      transform: translateX(0);
    }
  }
</style>