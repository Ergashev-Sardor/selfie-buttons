<template>
  <div id="overlay" :class="{ 'active': isActive }">
    <div class="text">
      <h1>Simple Drawer Menu</h1>
      <p>This is just a simple drawer menu. Creating it with HTML CSS and JS. I users Event listeners to toggle
        the class "active" in each part of the menu and used css to manipulate the style of the active class.
        You can click the links for my Instagram and my Github! if the screen is less than 600px the menu button
        will go to the bottom right for Ease of use on mobile.
      </p>
    </div>
    <div id="burger" :class="{ 'active': isActive }" @click="toggleDrawer">
      <div class="line"></div>
      <div class="line"></div>
      <div class="line"></div>
    </div>
    <div id="nav" :class="{ 'active': isActive }">
      <ul>
        <li>
          <a target="_blank" href="https://github.com/FlorezAdam-FS/SimpleCodes">
            <i class="fab fa-github fa-2x"></i>
          </a></li>
        <li>
          <a target="_blank" href="https://www.instagram.com/hardbeingwoke/">
            <i class="fab fa-instagram-square fa-2x"></i>
          </a>
        </li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data: () => ({
    isActive: false,
  }),
  methods: {
    toggleDrawer() {
      this.isActive = !this.isActive
    }
  },
  mounted() {
    /*
        1. Метод для обработки клика на кнопку бургера
        2. Добавить классы для открытия и закрытия
     */

    // const nav = document.getElementById('nav');
    // const burger = document.getElementById('burger');
    // const overlay = document.getElementById('overlay');

    // burger.addEventListener('click', () => {
    //   burger.classList.toggle('active');
    //   nav.classList.toggle('active');
    //   overlay.classList.toggle('active');
    // });
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#overlay {
  font-family: "Poppins", sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  transition: 0.3s linear;
}

#overlay .active {
  width: 100%;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.7);
}

#burger {
  position: absolute;
  top: 20px;
  right: 20px;
  background: #17141d;
  padding: 1rem;
  z-index: 1000;
  cursor: pointer;
  transition: 0.3s linear;
  box-shadow: 2px 2px 5px #17141d;
}

#burger:hover {
  background-color: goldenrod;
}

.line {
  width: 22px;
  margin-bottom: 5px;
  height: 2px;
  background-color: white;
}

.line:last-child {
  margin-bottom: 0;
}

#nav {
  height: 100vh;
  width: 300px;
  display: flex;
  align-items: center;
  justify-content: center;
  background-color: #17141d;
  color: white;
  position: fixed;
  right: 0;
  transform: translateX(100%);
  transition: transform 0.3s linear;
  margin-left: 200px;
}

#nav.active {
  transform: translateX(0);
}

ul {
  list-style: none;
  text-align: center;
}

li {
  text-transform: uppercase;
  font-size: 2rem;
  letter-spacing: 3px;
  line-height: 1.6;
}

.text {
  width: 80%;
  text-align: center;
  line-height: 1.8;
  letter-spacing: 3px;
}

h1 {
  margin-bottom: 3rem;
}

a {
  color: #fafafa;
  transition: 0.3s linear;
}

i {
  margin: 2rem;
}

a:hover {
  color: goldenrod;
  outline: none;
}

@media screen and (max-width: 600px) {
  #burger {
    top: 90%;
    right: 12%;
  }
}

</style>
