<template>
  <nav class="navbar">
    <div class="navbar__logo">
      <a href="#" class="navbar__logo-link">
        <h1 class="navbar__name">Alexey Maximchik</h1>
        <span class="navbar__desc">Full Stack Developer</span>
      </a>
    </div>
    <ul class="navbar__list">
      <li class="navbar__item">
        <a href="#" class="navbar__link"> About</a>
      </li>
      <li class="navbar__item">
        <a href="#" class="navbar__link"> Portfolio</a>
      </li>
      <li class="navbar__item">
        <a href="#" class="navbar__link">Contacts</a>
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
    font-family: Roboto-Light, Arial, Helvetica, sans-serif;
    display: block;
    font-size: 14px;
    color: var(--brown);
  }
  &__link {
    display: flex;
    align-items: center;
    padding: 12px 0 10px;
    font-family: Roboto-Light, Arial, Helvetica, sans-serif;
    font-size: 15px;
    font-weight: 200px;
    color: var(--text);
  }
}
</style>
