<template>
<div class="progress-bar">
  <div class="icons">
    <div class="unlocked-icon" v-for="index in levels.keys()" :key="index">
      <check size=10 v-if="isUnlocked(index)"></check>
      <lock size=8 color="#727282" v-else></lock>
    </div>
  </div>
  <div class="bar">
    <svg viewBox="0 0 780 8" xmlns="http://www.w3.org/2000/svg">
      <rect x="0" y="0" width="780" height="8" fill="#373745"/>
      <rect x="0" y="0" :width="progress * 780 + 60" height="8" fill="#B09976"/>
    </svg>
  </div>
  <div class="points">
    <div v-for="(level, index) in levels" :key="level.pointsToUnlock" class="points-label" :class="isUnlocked(index) ? 'points-active' : 'points-passive'">
      <span>{{level.pointsToUnlock}} </span>
      <point :color="isUnlocked(index) ? '#B09976' : '#888895'" size=14></point>
    </div>
  </div>
</div>
</template>

<script>
import Check from "./icons/Check.vue"
import Lock from "./icons/Lock.vue"
import Point from "./icons/Point.vue"

export default {
  components: {Check, Lock, Point},
  props: {
    levels: Array,
    currentLevelIndex: Number
  },
  computed: {
    progress() {
      return this.currentLevelIndex / (this.levels.length - 1)
    }
  },
  methods: {
    isUnlocked(levelIndex) {
      return levelIndex <= this.currentLevelIndex;
    }
  }
}
</script>

<style>
.bar {
  padding: 0 8%;
  margin: 0 auto;
}

.progress-bar {
  margin-top: 14.5px;
}

.icons {
  display: flex;
  justify-content: space-around;
  align-content: flex-start;
}

.points {
  display: flex;
  justify-content: space-around;
  align-content: flex-start;
}

.unlocked-icon {
  width: 10px;
}

.points-label {
  font-weight: 900;
  width: 100%;
  text-align: center;
}

.points-active {
  color: #B09976;
}

.points-passive {
  color: #888895;
}
</style>