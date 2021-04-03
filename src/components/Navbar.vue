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
      display: block;
    }
  }
  &__overlay {
    position: fixed;
    top: 0;
    right: 0;
    bottom: 0;
    left: 0;
    visibility: hidden;
    opacity: 0;
    background-color: var(--overlay);
    transition: 0.3s;
    &_is-visible {
      visibility: visible;
      opacity: 1;
    }
  }
}

.hamburger {
  padding: 15px 15px;
  display: inline-block;
  cursor: pointer;
  transition-property: opacity, filter;
  transition-duration: 0.15s;
  transition-timing-function: linear;
  font: inherit;
  color: inherit;
  text-transform: none;
  background-color: transparent;
  border: 0;
  margin: 0;
  overflow: visible;
}
.hamburger:hover {
  opacity: 0.7;
}
.hamburger.is-active:hover {
  opacity: 0.7;
}
.hamburger.is-active .hamburger-inner,
.hamburger.is-active .hamburger-inner::before,
.hamburger.is-active .hamburger-inner::after {
  background-color: #000;
}

.hamburger-box {
  width: 40px;
  height: 24px;
  display: inline-block;
  position: relative;
}

.hamburger-inner {
  display: block;
  top: 50%;
  margin-top: -2px;
}
.hamburger-inner,
.hamburger-inner::before,
.hamburger-inner::after {
  width: 40px;
  height: 4px;
  background-color: #000;
  border-radius: 4px;
  position: absolute;
  transition-property: transform;
  transition-duration: 0.15s;
  transition-timing-function: ease;
}
.hamburger-inner::before,
.hamburger-inner::after {
  content: '';
  display: block;
}
.hamburger-inner::before {
  top: -10px;
}
.hamburger-inner::after {
  bottom: -10px;
}
.hamburger--spin .hamburger-inner {
  transition-duration: 0.22s;
  transition-timing-function: cubic-bezier(0.55, 0.055, 0.675, 0.19);
}
.hamburger--spin .hamburger-inner::before {
  transition: top 0.1s 0.25s ease-in, opacity 0.1s ease-in;
}
.hamburger--spin .hamburger-inner::after {
  transition: bottom 0.1s 0.25s ease-in,
    transform 0.22s cubic-bezier(0.55, 0.055, 0.675, 0.19);
}

.hamburger--spin.is-active .hamburger-inner {
  transform: rotate(225deg);
  transition-delay: 0.12s;
  transition-timing-function: cubic-bezier(0.215, 0.61, 0.355, 1);
}
.hamburger--spin.is-active .hamburger-inner::before {
  top: 0;
  opacity: 0;
  transition: top 0.1s ease-out, opacity 0.1s 0.12s ease-out;
}
.hamburger--spin.is-active .hamburger-inner::after {
  bottom: 0;
  transform: rotate(-90deg);
  transition: bottom 0.1s ease-out,
    transform 0.22s 0.12s cubic-bezier(0.215, 0.61, 0.355, 1);
}
</style>
