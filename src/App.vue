<template>
  <div id="overlay">
    <div class="text">
      <h1>Simple Drawer Menu</h1>
      <p>This is just a simple drawer menu. Creating it with HTML CSS and JS. I users Event listeners to toggle
        the class "active" in each part of the menu and used css to manipulate the style of the active class.
        You can click the links for my Instagram and my Github! if the screen is less than 600px the menu button
        will go to the bottom right for Ease of use on mobile.
      </p>
    </div>
    <div id="burger" class="hamburger" v-on:click="toggleDrawer" v-bind:class="{ 'active': isActive }">
      <span></span>
      <span></span>
      <span></span>
    </div>
    <div id="nav" class="nav-menu" v-on:click="toggleDrawer" v-bind:class="{ 'active': isActive }">
      <div class="nav-menu__list">
        <div class="nav-menu__list-item">First link</div>
        <div class="nav-menu__list-item">Second link</div>
        <div class="nav-menu__list-item">Third link</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'hello-world',
  data: () => ({
    isActive: false,
  }),
  methods: {
      toggleDrawer() {
        this.isActive = !this.isActive
      }
  }

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
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

#overlay {
  background: aquamarine;
  font-family: "Poppins", sans-serif;
  margin: 0;
  padding: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 100vh;
  transition: 0.5s all
}

#overlay.active {
  width: 300px;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
}

.hamburger {
  position: absolute;
  width: 30px;
  top: 40px;
  right: 30px;
}
span {
  height: 2px;
  width: 100%;
  display: block;
  background: black;
  margin-bottom: 6px;/*
  transition: 0.2s all;*/
  &:last-child {
    margin-bottom: 0;
  }
}/*
.hamburger.active span:nth-child(1) {
  transform: translateY(3px) rotate(-45deg);
  margin-bottom: -2px;
  z-index: 100;
  position: absolute;
  transition: 0.7s all;
}
.hamburger.active span:nth-child(2) {
  display: none;
  margin-bottom: -2px;
}
.hamburger.active span:nth-child(3) {
  transform: translateY(3px) rotate(45deg);
  margin-bottom: -2px;
  z-index: 100;
  position: absolute;
  transition: 0.7s all;
}*/

.nav-menu {
  position: fixed;
  height: 100vh;
  top: 0;
  right: -100%;
  width: 25%;
  background: #fafafa;
  z-index: 20;
  transition: 1.27s all;
}
.nav-menu__list {
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
  align-items: center;
  height: 100%;
}
.nav-menu__list-item {
  margin-right: 0;
  font-size: 18px;
  color: #000000;
}
.nav-menu.active {
  display: block;
  right: 0;
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
  color: #000000;
  transition: 0.3s linear;
}

i {
  margin: 2rem;
}

a:hover {
  color:  #1c4d13;
  outline: none;
}

@media screen and (max-width: 600px) {
  #burger {
    top: 90%;
    right: 12%;
  }
}

</style>
