<template>
  <div>
    <Navbar />
    <main class="main">
      <TitleSection />
    </main>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import TitleSection from './components/TitleSection.vue';

export default {
  components: {
    Navbar, TitleSection,
  },
};
</script>

<style lang="scss">
@font-face {
  font-family: Roboto;
  src: url('./assets/fonts/Roboto-Regular.ttf');
}

@font-face {
  font-family: Roboto-Thin;
  src: url('./assets/fonts/Roboto-Thin.ttf');
}

@font-face {
  font-family: Roboto-Light;
  src: url('./assets/fonts/Roboto-Light.ttf');
}

:root {
  --teal: #008073;
  --brown: #795548;
  --light-gray: #fafafa;
  --gray: #ddd;
  --text: #333;
  --overlay: rgba(0, 0, 0, 0.5);
}

body {
  margin: 0;
  font-family: Roboto, Arial, Helvetica, sans-serif;
  background: url('./assets/images/bg.png');
}

h1,
h2,
h3 {
  margin: 0;
}

ul {
  list-style: none;
  margin: 0;
  padding: 0;
}

a {
  color: inherit;
  text-decoration: none;
}

.main {
  margin-left: 210px;
  @media(max-width: 992px) {
    margin-top: 65px;
    margin-left: 0;
  }
}
</style>
