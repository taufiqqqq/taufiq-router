<script setup>
// This starter template is using Vue 3 <script setup> SFCs
// Check out https://v3.vuejs.org/api/sfc-script-setup.html#sfc-script-setup
import HelloWorld from './components/HelloWorld.vue'
</script>


<template>
<div>
    <div class="sidebar">
      <div class="side-brand">
          GPP System
      </div>
      <div class="side-menus">
        <router-link to="/" class="side-menu active">
          <span class="side-icon"><i class="fa-solid fa-house-chimney"></i></span>
          <span class="side-text">Home</span>
        </router-link>
        <router-link to="/admin" class="side-menu">
          <span class="side-icon"><i class="fa-solid fa-chart-line"></i></span>
          <span class="side-text">Admin</span>
        </router-link>
      </div>
    </div>
    <router-view class="view" />
</div>
</template>

<script>
export default {
  mounted() {
    const list = document.querySelectorAll('.side-menu');
    function activeLink() {
      list.forEach((item) => item.classList.remove('active'));
      this.classList.add('active');
    }
    list.forEach((item) => item.addEventListener('click', activeLink));
  },
}
</script>

<style>
* {
  margin: 0;
  box-sizing: border-box;
  font-family: Franklin Gothic Medium;
}
body {
  background-color: white;
  color: white;
}
.sidebar {
  position: fixed;
  inset: 0;
  width: 15rem;
  background: lightskyblue;
  display: flex;
  flex-direction: column;
}
.side-brand {
  width: 100%;
  height: 8rem;
  font-size: 2rem;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
}
.side-menus {
  font-size: 1rem;
  width: 100%;
  font-weight: bold;
}
.side-menu {
  display: flex;
  padding: 1rem 0;
  text-decoration: none;
  color: white;
}
.side-menu:hover, .active {
  background-color: lightgray;
  color: white;
  font-weight: bolder;
  cursor: pointer;
  transition: .2s;
}
.side-icon {
  width: 1rem;
  display: flex;
  align-items: center;
  justify-content: center;
}
.view {
  width: calc(100% - 15rem);
  transform: translateX(20rem);
  height: 100%;
  color: black;
}
.page {
  padding: 2rem;
  font-size: 2rem;
  font-weight: bold;
}
</style>