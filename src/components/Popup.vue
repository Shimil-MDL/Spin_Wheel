<template>
    <div class="popUp">
      <h1>Heyy {{ name }}</h1>
      <h2>Your dare is "{{ dare }}"</h2>
    </div>
</template>

<script>
export default {
  name: "Popup",
  props: ['name','dare'],
};
</script>

<style>
.popUp {
  position: absolute;
  top: 50%;
  left: 50%;
  border: 3px solid rgba(255, 255, 255, 0.3);
  backdrop-filter: blur(15px);
  display: flex;
  justify-content: space-around;
  align-items: center;
  flex-direction: column;
  padding: 20px;
  padding-top: 6%;
  padding-bottom: 10%;
  width: 40vw;
  height: 65vh;
  z-index: 10;
  border-radius: 10px;
  transform: translate(-50%, -50%);
  cursor: pointer;
}


</style>