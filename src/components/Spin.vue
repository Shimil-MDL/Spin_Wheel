<template>
  <div class="spin" @click="spinDare()">😉</div>
  <div class="wheel-outer">
    <div class="wheel-inner">
      <div class="red"></div>
      <div class="text r">34</div>

      <div class="blue"></div>
      <div class="text b">10</div>

      <div class="amber"></div>
      <div class="text a">81</div>

      <div class="green"></div>
      <div class="text g">56</div>

      <div class="indigo"></div>
      <div class="text i">8</div>

      <div class="purple"></div>
      <div class="text pu">13</div>

      <div class="pink"></div>
      <div class="text pi">99</div>

      <div class="orange"></div>
      <div class="text o">26</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Spin",
  components: {},
  data() {
    return {
      click: 0,
      rotate: 0,
    };
  },
  emits: ['popup'],
  methods: {
    spinDare() {
      let wheel = document.querySelector(".wheel-outer");
      if (this.click !== 8) {
        this.click += 1;
        this.rotate = this.click * 135 + this.click * 720;
        wheel.style.transition = "3s cubic-bezier(.33,.66,.2,1)";
      } else {
        this.click = 0;
        this.rotate = 0;
        wheel.style.transition = "0s";
      }
      this.$emit('popup',this.click-1)
      wheel.style.transform = `scale(1.5) rotate(${this.rotate}deg)`;
    },
  },
};
</script>

<style scoped>
.wheel-outer {
  --red: #ef5350;
  --blue: #3b82f6;
  --amber: #fbbf24;
  --green: #10b981;
  --indigo: #3d5afe;
  --purple: #7e57e2;
  --pink: #f06292;
  --orange: #ff6e40;
  height: 300px;
  width: 300px;
  border-radius: 50%;
  margin: auto;
  box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.1),
    -3px -3px 6px rgba(255, 255, 255, 0.7);

  display: flex;
  align-items: center;
  justify-content: center;

  transition: 2s;

  transform: scale(1.5);
}
.wheel-inner {
  position: relative;
  width: 270px;
  height: 270px;
  border-radius: 50%;
  box-shadow: inset 3px 3px 6px rgba(0, 0, 0, 0.25),
    inset -3px -3px 6px rgba(255, 255, 255, 0.4);
  display: flex;
  align-items: center;
  justify-content: center;
  overflow: hidden;
}
.spin {
  background: #dedede;
  font-size: 1.5rem;
  width: 60px;
  height: 60px;
  border-radius: 50%;
  box-shadow: 3px 3px 6px rgba(0, 0, 0, 0.25),
    -3px -3px 6px rgba(255, 255, 255, 0.4);
  z-index: 5;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%) scale(1.5);
  display: flex;
  align-items: center;
  justify-content: center;
  cursor: pointer;

  /* display: none; */
}
.spin:active {
  box-shadow: inset 3px 3px 6px rgba(0, 0, 0, 0.25),
    inset -3px -3px 6px rgba(255, 255, 255, 0.4);
  font-size: 1.1rem;
}
.spin::before {
  content: "";
  position: absolute;
  transform: translateY(-140%) rotate(45deg);
  width: 18px;
  height: 18px;
  border-radius: 3px;
  background: inherit;
}
.red,
.blue,
.amber,
.green,
.indigo,
.purple,
.pink,
.orange {
  position: absolute;
  width: 0;
  height: 0;
  border-right: 60px solid transparent;
  border-left: 60px solid transparent;
  border-bottom: 150px solid var(--red);

  transform: rotate(90deg) translateY(70px);
  z-index: 1;
  display: flex;
}
.blue {
  border-bottom: 150px solid var(--blue);
  transform: rotate(-90deg) translateY(70px);
}
.amber {
  border-bottom: 150px solid var(--amber);
  transform: rotate(0deg) translateY(70px);
}
.green {
  border-bottom: 150px solid var(--green);
  transform: rotate(-45deg) translateY(70px);
}
.indigo {
  border-bottom: 150px solid var(--indigo);
  transform: rotate(-135deg) translateY(70px);
}
.purple {
  border-bottom: 150px solid var(--purple);
  transform: rotate(180deg) translateY(70px);
}
.pink {
  border-bottom: 150px solid var(--pink);
  transform: rotate(135deg) translateY(70px);
}
.orange {
  border-bottom: 150px solid var(--orange);
  transform: rotate(45deg) translateY(70px);
}
.r {
  color: var(--red);
  transform: rotate(-90deg) translateY(-250%);
}
.b {
  color: var(--blue);
  transform: rotate(90deg) translateY(-250%);
}
.a {
  color: var(--amber);
  transform: rotate(180deg) translateY(-250%);
}
.g {
  color: var(--green);
  transform: rotate(135deg) translateY(-250%);
}
.i {
  color: var(--indigo);
  transform: rotate(45deg) translateY(-250%);
}
.pu {
  color: var(--purple);
  transform: translateY(-250%);
}
.pi {
  color: var(--pink);
  transform: rotate(-45deg) translateY(-250%);
}
.o {
  color: var(--orange);
  transform: rotate(-135deg) translateY(-250%);
}

.text {
  width: 40px;
  height: 40px;
  border-radius: 50%;
  background: rgba(224, 224, 224, 0.7);
  position: absolute;
  z-index: 2;

  font-size: 1.5rem;
  font-family: "Montserrat";
  font-weight: bold;
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>