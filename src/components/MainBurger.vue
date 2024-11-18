<template>
  <button class="btn-reset burger">
    <span class="burger__line"></span>
  </button>
</template>

<style lang="scss">
  .burger{
    display: block;
    position: relative;
    z-index: 10;
    width: 40px;
    height: 20px;
    color: var(--rum-color);
    &__line{
      position: absolute;
      top: 50%;
      left: 0;
      width: 100%;
      height: 2px;
      background-color: currentColor;
      transform: translateY(-50%);
      transition: .3s ease;
    }
    &::after, &::before{
      content: "";
      position: absolute;
      left: 0;
      width: 100%;
      height: 2px;
      background-color: currentColor;
      transition: .3s ease;
    }
    &::before{
      content: "";
      top: 0;
    }
    &::after{
      content: "";
      bottom: 0;
    }
    &.active-burger .burger__line{
      display: none;
    }
    &.active-burger::after{
      bottom: 9px;
      rotate: -45deg;
    }
    &.active-burger::before {
      top: 9px;
      rotate: 45deg;
    }
  }
</style>