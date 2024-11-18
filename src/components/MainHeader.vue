<script setup>
  import Nav from './MainNav.vue'
  import Burger from "@/components/MainBurger.vue";
  import {ref} from "vue";

  const activeBurger = ref(false);
  const activeNav = ref(false);
  const toggleActive = () => {
    activeBurger.value = !activeBurger.value;
    activeNav.value = !activeNav.value;
    if (activeBurger.value) {
      document.body.classList.add("no-scroll");
    } else {
      document.body.classList.remove("no-scroll");
    }
  }

</script>

<template>
  <header class="header">
    <div class="container header__container">
      <a href="#" class="header__logo">
        <img loading="lazy" src="/logo.png" alt="Site logo" width="280" height="78">
      </a>
      <Nav class="header__nav" :class="{ 'active-nav': activeNav }"/>
      <Burger class="header__burger" @click="toggleActive()" :class="{ 'active-burger': activeBurger }"/>
    </div>
  </header>
</template>

<style scoped lang="scss">
  .header{
    position: absolute;
    top: 0;
    padding: 10px 0;
    width: 100%;
    &__container {
      display: flex;
      align-items: center;
      justify-content: space-between;
    }
    &__logo{
      @media (max-width: 1024px) {
        width: 200px;
      }
    }
    &__button{
      margin-left: 55px;
      @media (max-width: 1024px){
        margin: 0;
      }
    }
    //&__nav{
    //  @media (max-width: 1024px) {
    //    display: none;
    //  }
    //}
    &__burger{
      display: none;
      @media (max-width: 1024px) {
        display: block;
      }
    }
  }
</style>