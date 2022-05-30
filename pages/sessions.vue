<template>
  <div class="container">
    <div class="marco">
      <img v-show="namasendaShown" src="/namasenda1.png" />
      <img v-show="!namasendaShown" src="/namasendadelay.png" />
      <div class="menu" @click="showMenu()">MENU</div>
      <div v-show="isShown" class="lateralMenu">
        <div class="closeButton" @click="showMenu()">X</div>
        <ul>
          <nuxt-link :to="'/'">
            <li>HOME</li>
          </nuxt-link>
          <li>CHATS</li>
          <nuxt-link :to="'/sessions'">
            <li>SESSIONS</li>
          </nuxt-link>
          <li>PERSPECTIVE</li>
          <nuxt-link :to="'/newsounds'">
            <li>NEW SOUNDS</li>
          </nuxt-link>
          <li>ON GENDER</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      isShown: false,
      namasendaShown: true,
    };
  },
  methods: {
    showMenu() {
      if (this.isShown) {
        this.isShown = false;
      } else {
        this.isShown = true;
      }
    },
  },
  created() {
      setTimeout(() => {
      this.namasendaShown = false;
    }, 2000);
  },
};
</script>

<style>


*{
  font-family: 'Conthrax';
}
.container {
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}
img {
  height: 700px;
  object-fit: cover;
}
.marco {
  position: relative;
}

.menu {
  position: absolute;
  padding: 10px;
  background-color: white;
  display: inline;
  border-radius: 999px;
  left: 20px;
  top: 20px;
  z-index: 3;
  font-weight: bold;
  color: black;
  user-select: none; /* supported by Chrome and Opera */
   -webkit-user-select: none; /* Safari */
   -khtml-user-select: none; /* Konqueror HTML */
   -moz-user-select: none; /* Firefox */
   -ms-user-select: none; /* Internet Explorer/Edge */
}

body {
  background-color: black;
}
.lateralMenu{
  position: absolute;
  top: 0;
  left: 0;
  background-color: rgba(0,0,0,0.5);
  height: 700px;
  width: 300px;
  z-index: 4;
  padding: 20px;
  transition: all 0.2s;
}

ul{
  list-style-type: none;
  display: flex;
  flex-direction: column;
  gap: 20px;
  padding-top: 36px;
}

.closeButton{
  padding: 10px;
  background-color: white;
  color: black;
  display: inline;
  border-radius: 999px;
  user-select: none; /* supported by Chrome and Opera */
   -webkit-user-select: none; /* Safari */
   -khtml-user-select: none; /* Konqueror HTML */
   -moz-user-select: none; /* Firefox */
   -ms-user-select: none; /* Internet Explorer/Edge */
}

li{
  border: 2px solid white;
  border-radius: 9999px;
  padding: 10px;
  display: flex;
  justify-content: center;
  color: white;
  font-weight: bold;
  font-size: 19px;
}
</style>
