<template>
  <div class="counter-container">
    <h1 class="counter-title"> НАКОПЛЕНО ПОИНТОВ </h1>
    <div class="counter-points"> 2 560 <point size=25 color="#FFFFFF"></point> </div>
    <next-level></next-level>
    <div class="counter-text"> До следующего уровня осталось </div>
    <div class="counter-points-left"> 1000 <point color="#FFFFFF"></point> </div>
    <hr class="counter-divider">
    <div class="timer">
      <div class="timer-segment">
        <div class="timer-label">дн.</div>
        <div class="clock">30</div>
      </div>
      <div class="timer-divider">:</div>
      <div class="timer-segment">
        <div class="timer-label">ч.</div>
        <div class="clock">22</div>
      </div>
      <div class="timer-divider">:</div>
      <div class="timer-segment">
        <div class="timer-label">мин.</div>
        <div class="clock">06</div>
      </div>
      <div class="timer-divider">:</div>
      <div class="timer-segment">
        <div class="timer-label">сек.</div>
        <div class="clock">11</div>
      </div>
      
    </div>
    
  </div>
</template>

<script>
import Point from "./icons/Point.vue"
import NextLevel from "./icons/NextLevel.vue"

export default {
  components: {Point, NextLevel}
}
</script>

<style>
.counter-container {
  width: 356px;
  background-color: #2C2C39;
  margin-left: 8px;
  text-align: center;
  padding: 42px 16px 16px 16px;
  color: white;
}
.counter-title {
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  margin-top: 0;
  margin-bottom: 8px;
}
.counter-points {
  font-weight: 900;
  font-size: 60px;
  line-height: 70px;
  margin-bottom: 24px;
}
.counter-text {
  margin: 4px 0;
  font-size: 12px;
  line-height: 14px;
}
.counter-points-left {
  font-weight: 900;
  font-size: 16px;
  line-height: 19px;
  margin-bottom: 13px;
}
.timer {
  margin-top: 13px;
  display: flex;
  justify-content: center;
}
.timer-segment {
  margin: 0 8px;
}
.timer-divider {
  margin-top: 18px;
}
.clock {
  font-weight: 500;
  font-size: 24px;
  line-height: 28px;
  color: #AFAFB5;
  text-align: center;
}
.timer-label {
  color: #727282;
  font-size: 12px;
  line-height: 14px;
  text-align: center;
}
hr.counter-divider {
  border: none;
  height: 1px;
  background-color: #373745;
}
</style>