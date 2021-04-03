<template>
  <nav class="navbar">
    <div
      class="navbar__plank"
      :class="{
        'navbar__plank_without-box-shadow': isMobileMenuVisible,
      }"
    >
      <button
        class="hamburger hamburger--spin"
        :class="{ 'is-active': isMobileMenuVisible }"
        @click="toggleMobileMenu"
      >
        <div class="hamburger-box">
          <div class="hamburger-inner"></div>
        </div>
      </button>
      <a class="navbar__title">
        <h2 class="navbar__plank-name">Alexey Maximchik</h2>
        <span class="navbar__plank-desc">Full Stack Developer</span>
      </a>
    </div>
    <ul
      class="navbar__list"
      :class="{
        'navbar__list_is-active': isMobileMenuVisible,
      }"
    >
      <li class="navbar__logo">
        <a href="#" class="navbar__logo-link">
          <h1 class="navbar__name">Alexey Maximchik</h1>
          <span class="navbar__desc">Full Stack Developer</span>
        </a>
      </li>
      <li class="navbar__item" v-for="(item, index) in navLinks" :key="index">
        <a href="#" class="navbar__link" :class="`navbar__link_${index + 1}`">
          <img :src="item.icon" alt="Navigation icon" class="navbar__icon" />
          {{ item.name }}</a
        >
      </li>
    </ul>
    <div
      class="navbar__overlay"
      @click="isMobileMenuVisible = false"
      :class="{
        'navbar__overlay_is-visible': isMobileMenuVisible,
      }"
    ></div>
  </nav>
</template>

<script>
import AboutIcon from '../assets/icons/person.svg';
import PortfolioIcon from '../assets/icons/web.svg';
import ContractsIcon from '../assets/icons/mail.svg';

export default {
  data: () => ({
    navLinks: [
      {
        name: 'About',
        link: '#',
        icon: AboutIcon,
      },
      {
        name: 'Portfolio',
        link: '#',
        icon: PortfolioIcon,
      },
      {
        name: 'Contacts',
        link: '#',
        icon: ContractsIcon,
      },
    ],
    isMobileMenuVisible: false,
  }),
  methods: {
    toggleMobileMenu() {
      this.isMobileMenuVisible = !this.isMobileMenuVisible;
    },
  },
};
</script>

<style lang="scss" scoped>
@import url('../assets/styles/hamburger.scss');

.navbar {
  &__logo {
    padding: 30px 30px 40px 30px;
    background-color: var(--light-gray);
    border-bottom: 1px solid var(--gray);
    @media (max-width: 992px) {
      display: none;
    }
  }
  &__name {
    margin-bottom: 7px;
    font-family: Roboto-Thin, Arial, Helvetica, sans-serif;
    font-size: 31.5px;
    font-weight: 200;
    line-height: 100%;
    color: var(--teal);
  }
  &__desc {
    display: block;
    font-family: Roboto-Light, Arial, Helvetica, sans-serif;
    font-size: 14px;
    color: var(--brown);
  }
  &__list {
    position: fixed;
    top: 0;
    left: 0;
    width: 210px;
    height: 100%;
    background-color: #fff;
    box-shadow: 0 2px 5px 0 rgb(0 0 0 / 16%), 0 2px 10px 0 rgb(0 0 0 / 12%);
    z-index: 1;
    @media (max-width: 992px) {
      margin-top: 65px;
      transform: translateX(-220px);
      transition: 0.3s;
    }
    &_is-active {
      transform: none;
    }
  }
  &__item {
    transition: 0.3s;
    &:hover {
      background-color: var(--gray);
    }
  }
  &__link {
    display: flex;
    align-items: center;
    padding: 10px 0 12px;
    font-family: Roboto-Light, Arial, Helvetica, sans-serif;
    font-size: 15px;
    color: var(--text);
    transition: 0.3s;
    &_1 {
      &:hover {
        border-left: 3px solid #008073;
      }
    }
    &_2 {
      &:hover {
        border-left: 3px solid #3f51b5;
      }
    }
    &_3 {
      &:hover {
        border-left: 3px solid #795548;
      }
    }
    &:hover {
      background-color: var(--light-gray);
    }
  }
  &__icon {
    padding: 0 15px;
  }
  &__plank {
    position: fixed;
    top: 0;
    display: none;
    justify-content: center;
    align-items: center;
    width: 100%;
    height: 65px;
    background: #fff;
    box-shadow: 0 2px 5px 0 rgb(0 0 0 / 16%), 0 2px 10px 0 rgb(0 0 0 / 12%);
    z-index: 2;
    transition: 0.3s;
    &_without-box-shadow {
      box-shadow: none;
    }
    @media (max-width: 992px) {
      display: flex;
    }
  }
  &__title {
    text-align: center;
  }
  &__plank-name {
    font-size: 22px;
    font-weight: 300;
    color: var(--teal);
  }
  &__plank-desc {
    font-family: Roboto-Light, Arial, Helvetica, sans-serif;
    font-size: 14px;
    font-weight: 200;
    color: var(--brown);
  }
  &__overlay {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    display: none;
    visibility: hidden;
    opacity: 0;
    background-color: var(--overlay);
    transition: 0.3s;
    &_is-visible {
      visibility: visible;
      opacity: 1;
    }
    @media (max-width: 992px) {
      display: block;
    }
  }
}
</style>
