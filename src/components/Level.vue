<template>
<div class="level" :class="isUnlocked && !isCurrentLevel ? 'unlocked-level' : ''">
    <div class="current-level-mark" v-if="isCurrentLevel"> Текущий уровень </div>
    <div class="stars">
        <star class="star" v-for="i in Array(index+1).keys()" :key="i" :color="isUnlocked ? '#B09976' : '#727282'"></star>
    </div>
    <div :class="[cardClass, 'level-card']"> 
        <div class="level-title"> LEVEL {{index+1}}</div>
        <div class="level-conditions"> 
            <div class="level-condition"> 
                <b>1</b> <point :color="iconsColor"></point> = <b>{{gemsPerPoint}}</b> <gem :color="iconsColor"></gem>
            </div>
            <hr :class="isUnlocked ? 'active' : 'passive'">
            <div class="level-condition"> 
                Бонус <b>{{bonusGems}}</b> <gem :color="iconsColor"></gem>
            </div>
            <hr :class="isUnlocked ? 'active' : 'passive'">
            <div class="level-condition"> Кэшбэк <b>{{cashback}}</b> %</div>
        </div>
    </div>
</div>
</template>

<script>
import Star from "./icons/Star.vue"
import Gem from "./icons/Gem.vue"
import Point from "./icons/Point.vue"

export default {
    components: {Star, Gem, Point},

    props: {
        index: Number,
        gemsPerPoint: Number,
        bonusGems: Number,
        cashback: Number,
        currentLevelIndex: Number
    },

    computed: {
        isCurrentLevel() {
            return this.index === this.currentLevelIndex;
        },
        isUnlocked() {
            return this.index <= this.currentLevelIndex;
        },
        cardClass() {
            return this.isUnlocked ? 'level-card-active' : 'level-card-passive'
        },
        iconsColor() {
            return this.isUnlocked ? "#FFFFFF" : "#AFAFB5"
        }
    }
}
</script>

<style>
.level {
    height: fit-content;
    flex-grow: 1;
}
.unlocked-level {
    opacity: 60%;
}
.stars {
    display: flex;
    justify-content: center;
    margin-bottom: 4px;
}
.star {
    margin: 0 2px;
}
.current-level-mark {
    font-family: Roboto;
    font-style: normal;
    font-weight: 500;
    font-size: 11px;
    line-height: 13px;
    text-align: center;
    margin-bottom: 12px;
    color: #B09976;
}
.level-card {
    margin: 0 auto;
    width: 100px;
    height: 150px;
    background-repeat: no-repeat;
    background-size: contain;
}
.level-card-passive {
    background-image: url("../assets/level-card.svg");
    color: #AFAFB5;
}
.level-card-active {
    background-image: url("../assets/level-card-active.svg");
}
.level-title {
    padding-top: 16px;
    margin: 0 auto;
    margin-bottom: 8px;
    font-family: Montserrat;
    font-style: normal;
    font-weight: 900;
    font-size: 12px;
    line-height: 15px;
    text-align: center;
}
.level-conditions {
    padding: 16px 8px 0px 8px;
}
.level-condition {
    font-weight: 500;
    line-height: 12px;
    font-size: 10px;
}
hr.passive {
    border: none;
    height: 1px;
    background-color: #AFAFB5;
    margin: 6px 0 6px 0;
}
hr.active {
    border: none;
    height: 1px;
    background-color: #B09976;
    margin: 6px 0 6px 0;
}

</style>