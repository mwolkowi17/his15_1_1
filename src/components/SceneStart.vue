<script setup lang="ts"></script>
<template>
  <div class="tlo">
    <div class="title-container">
      <div>
        <p>Podróż z Latarnikiem</p>
      </div>
    </div>
    <button class="button-start my-button">Start</button>
  </div>
</template>

<style style>
.tlo {
  background-image: url("../assets/plansza_his.png");
  background-size: 1920px 1080px;
  height: 1080px;
  width: 1920px;
  top: 0px;
  left: 0px;
  position: absolute;
  display: flex;
  flex-direction: column;
  /* justify-content: center; */
  align-items: center;
}

.title-container {
  position: absolute;
  width: 800px;
  height: 150px;
  background-color: #fff1e6;
  color: #093343;
  font-size: 60px;
  font-style: bold;
  font-weight: 500;
  font-family: "Proxima Nova", sans-serif;
  display: flex;
  justify-content: center;
  align-items: center;
  top: 719px;
}

.button-start {
  position: absolute;
  color: white;
  background-color: #900000;
  width: 260px;
  height: 93px;
  border-radius: 39px;
  font-size: 48px;
  font-style: bold;
  font-weight: 600;
  font-family: "Proxima Nova", sans-serif;
  top: 926px;
}

.button-start:focus {
  outline: 5px solid black;
  outline-offset: 10px;
}
</style>
