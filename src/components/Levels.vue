<template>
  <div class="levels">
    <h1 class="levels-title">УРОВЕНЬ В СЛЕДУЮЩЕМ МЕСЯЦЕ</h1>
    <div class="levels-container">
      <div v-for="(level, index) in levels" :key="index" @mouseover="setCurrentLevel(index)">
        <level :index="index" :currentLevelIndex="currentLevelIndex" :bonusGems="level.bonusGems" :gemsPerPoint="level.gemsPerPoint" :cashback="level.cashback"></level>
      </div>
    </div>
    <progress-bar :levels="levels" :currentLevelIndex="currentLevelIndex"></progress-bar>
  </div>
</template>

<script>
import Level from "./Level.vue"
import ProgressBar from "./ProgressBar.vue"

export default {
  components: { Level, ProgressBar },
  data() {
    return {
      currentLevelIndex: 3,
      levels: [
        {
          gemsPerPoint: 0,
          bonusGems: 0,
          cashback: 5,
          pointsToUnlock: 0
        },
        {
          gemsPerPoint: 3,
          bonusGems: 500,
          cashback: 5,
          pointsToUnlock: 50
        },
        {
          gemsPerPoint: 4,
          bonusGems: 1000,
          cashback: 6,
          pointsToUnlock: 1000
        },
        {
          gemsPerPoint: 5,
          bonusGems: 2500,
          cashback: 7,
          pointsToUnlock: 5000
        },
        {
          gemsPerPoint: 5,
          bonusGems: 5000,
          cashback: 10,
          pointsToUnlock: 25000
        },
        {
          gemsPerPoint: 5,
          bonusGems: 10000,
          cashback: 15,
          pointsToUnlock: 100000
        },
      ]
    }
  },
  methods: {
    setCurrentLevel(index) {
      console.log("hello");
      this.currentLevelIndex = index;
    }
  }
}

</script>

<style>
.levels {
  padding: 16px;
  background-color: #1E1E27;
  flex-grow: 1;
}
.levels-title {
  font-family: Roboto;
  font-style: normal;
  font-weight: 500;
  font-size: 12px;
  line-height: 14px;
  color: white;
  margin-top: 0;
  margin-bottom: 16px;
}
.levels-container {
  display: flex;
  justify-content: space-around;
  align-items: flex-end;
}
</style>