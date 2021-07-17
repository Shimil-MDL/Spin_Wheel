<template>
    <div class="popUp">
      <div> ✖ </div>
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
.popUp div{
position: absolute;
font-size: 2rem;
right: 2%;
top: 2%;
transition: color 0.5s;
}
.popUp div:hover{
color: #c4c4c4;
}



</style>
