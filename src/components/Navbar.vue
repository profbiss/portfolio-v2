<template>
  <nav class="navbar">
    <ul class="navbar__list">
      <li class="navbar__logo">
        <a href="#" class="navbar__logo-link">
          <h1 class="navbar__name">Alexey Maximchik</h1>
          <span class="navbar__desc">Full Stack Developer</span>
        </a>
      </li>
      <li class="navbar__item">
        <a href="#" class="navbar__link">
          <img src="../assets/icons/person.svg" alt="Navigation icon" class="navbar__icon">
          About</a>
      </li>
      <li class="navbar__item">
        <a href="#" class="navbar__link">
          <img src="../assets/icons/web.svg" alt="Navigation icon" class="navbar__icon">
          Portfolio</a>
      </li>
      <li class="navbar__item">
        <a href="#" class="navbar__link">
          <img src="../assets/icons/mail.svg" alt="Navigation icon" class="navbar__icon">
          Contacts</a>
      </li>
    </ul>
  </nav>
</template>

<script>
export default {};
</script>

<style lang="scss" scoped>
.navbar {
  position: fixed;
  top: 0;
  left: 0;
  width: 210px;
  height: 100%;
  background-color: #fff;
  box-shadow: 0 2px 5px 0 rgb(0 0 0 / 16%), 0 2px 10px 0 rgb(0 0 0 / 12%);
  &__logo {
    padding: 30px 30px 40px 30px;
    background-color: var(--light-gray);
    border-bottom: 1px solid var(--gray);
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
  &__link {
    display: flex;
    align-items: center;
    padding: 10px 0 12px;
    font-family: Roboto-Light, Arial, Helvetica, sans-serif;
    font-size: 15px;
    color: var(--text);
  }
  &__icon {
    padding: 0 15px;
  }
}
</style>
