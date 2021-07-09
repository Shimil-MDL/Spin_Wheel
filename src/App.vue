<template>
  <div class="cardContainer">
    <div
      class="card"
      v-for="card in cards"
      :key="card.num"
      :style="{ 'background-color': card.color }"
    >
      <div class="title">{{ card.num }}</div>
      <input type="text" placeholder="Enter the name" v-model="card.name" />
      <input
        type="text"
        placeholder="Enter the nickname"
        v-model="card.nickname"
      />
    </div>
  </div>

  <div class="btn" @click="enterGame">Enter the dare</div>
  <div class="dare">
    <Spin @popup="spinned"/>

      <transition name="pop">
        <Popup v-if="value === 0"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>
      
      <transition name="pop">
        <Popup v-if="value === 1"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

      <transition name="pop">
        <Popup v-if="value === 2"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

      <transition name="pop">
        <Popup v-if="value === 3"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

      <transition name="pop">
        <Popup v-if="value === 4"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

      <transition name="pop">
        <Popup v-if="value === 5"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

      <transition name="pop">
        <Popup v-if="value === 6"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

      <transition name="pop">
        <Popup v-if="value === 7"
          :name="cards[value].name"
          :nickname="cards[value].nickname"
          :dare="cards[value].dare"
          :style="{backgroundColor: cards[value].colorfade}"
          @click="value = -1"
        />
      </transition>

  </div>
</template>

<script>
import Spin from "./components/Spin";
import Popup from "./components/Popup";

export default {
  name: "App",
  components: {
    Spin,
    Popup,
  },
  data() {
    return {
      name: "",
      value: -1,
      cards: [
        {
          num: 26,
          color: "#ff6e40",
          colorfade: "#ff6e40df",
          name: "",
          nickname: "",
          dare: "Sing a song...",
        },
        {
          num: 10,
          color: "#3d5afe",
          colorfade: "#3d5afedf",
          name: "",
          nickname: "",
          dare: "Mimic the person who chose number 56...",
        },
        {
          num: 99,
          color: "#f06292",
          colorfade: "#f06292df",
          name: "",
          nickname: "",
          dare: "Dance to a song...",
        },
        {
          num: 81,
          color: "#fbbf24",
          colorfade: "#fbbf24df",
          name: "",
          nickname: "",
          dare: "Sing a song...",
        },
        {
          num: 8,
          color: "#3b82f6",
          colorfade: "#3b82f6df",
          name: "",
          nickname: "",
          dare: "Mimic the person who chose number 34...",
        },
        {
          num: 34,
          color: "#ef5350",
          colorfade: "#ef5350df",
          name: "",
          nickname: "",
          dare: "Sing a song...",
        },
        {
          num: 56,
          color: "#10b981",
          colorfade: "#10b981df",
          name: "",
          nickname: "",
          dare: "Sing a song...",
        },
        {
          num: 13,
          color: "#7e57e2",
          colorfade: "#7e57e2df",
          name: "",
          nickname: "",
          dare: "Dance to a song...",
        },
      ],
    };
  },
  // emits: ['popup'],
  methods: {
    enterGame() {
      document.querySelector(".dare").scrollIntoView();
    },
    spinned(click){
      this.value = click
    },
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
body {
  min-height: 100vh;
  background: #dedede;
  overflow-x: hidden;
}
html {
  scroll-behavior: smooth;
}
::-webkit-scrollbar {
  width: 14px;
  height: 14px;
  background-color: transparent;
}
::-webkit-scrollbar-thumb {
  border-radius: 10px;
  width: 10px;
  background: linear-gradient(141deg, #b98cc0 13%, #949494 40%);
}
::-webkit-scrollbar-thumb:hover {
  background: linear-gradient(238deg, #525050 12%, #787878 59%);
}
::-webkit-scrollbar-track {
  background-color: #f1efef;
}
::-webkit-scrollbar-corner {
  background: transparent;
}
#app {
  font-family: "Montserrat", sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;

  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
}
.dare {
  height: 100vh;
  width: 100vw;
  background: #dedede;
  overflow: hidden;
  display: flex;
  position: relative;
}
.cardContainer {
  height: 60vh;
  margin-top: 100px;

  display: flex;
  align-items: center;
  justify-content: space-evenly;
  align-content: space-evenly;
  flex-wrap: wrap;
}
.card {
  width: 300px;
  height: 250px;
  border-radius: 10px;
  padding: 25px 0px 45px 0;
  margin: 10px 20px 20px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-between;
  border: 3px solid #33333370;
}
.card .title {
  width: 50px;
  height: 50px;
  border-radius: 50%;
  background: rgba(224, 224, 224, 0.7);

  font-size: 1.8rem;
  font-family: "Montserrat";
  color: #252525;
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
}
.card input {
  appearance: none;
  border: none;
  outline: none;
  font-size: 1rem;
  font-family: "Montserrat";
  background: rgba(224, 224, 224, 0.7);
  color: #252525;
  width: 270px;
  border-radius: 5px;
  padding: 10px;
}
.btn {
  user-select: none;
  margin: 100px 0 50px;
  font-size: 20px;
  width: 200px;
  height: 60px;
  border-radius: 30px;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  box-shadow: 5px 5px 10px #00000059;
}
.btn:active {
  box-shadow: inset 3px 3px 6px #00000059;
}

.pop-enter-active{
  transition: opacity 1s 3.2s, transform 1s 3.2s;
}
.pop-leave-active {
  transition: opacity 1s 0.2s, transform 1s 0.2s;
}
.pop-enter-from,
.pop-leave-to {
  opacity: 0;
  transform: translate(-50%,-120%);
}

</style>
