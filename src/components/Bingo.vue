<template>
  <div class="bingo">
    <h1>{{txtMessage}}</h1>
    <div class="current-num">{{currentNum}}</div>
    <div class="area-btn">
      <button v-if="startState" @click="changeCurrentNum" class="btn btn-start">START</button>
      <button @click="reset" class="btn btn-reset">RESET</button>
    </div>
    <div class="container">
      <ul class="number-list">
        <li v-for="n of totalNum" :key="n" :class="{ displayed:numStateFlag[n] }">{{n}}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "bingo",
  data: () => ({
    txtMessage: "Bingo Game",
    numList: [
      1,
      2,
      3,
      4,
      5,
      6,
      7,
      8,
      9,
      10,
      11,
      12,
      13,
      14,
      15,
      16,
      17,
      18,
      19,
      20,
      21,
      22,
      23,
      24,
      25,
      26,
      27,
      28,
      29,
      30,
      31,
      32,
      33,
      34,
      35,
      36,
      37,
      38,
      39,
      40,
      41,
      42,
      43,
      44,
      45,
      46,
      47,
      48,
      49,
      50,
      51,
      52,
      53,
      54,
      55,
      56,
      57,
      58,
      59,
      60,
      61,
      62,
      63,
      64,
      65,
      66,
      67,
      68,
      69,
      70,
      71,
      72,
      73,
      74,
      75
    ],
    numStateFlag: [
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false,
      false
    ],
    totalNum: 0,
    currentNum: 0,
    startState: true
  }),
  created: function () {
    this.totalNum = this.numList.length
  },
  methods: {
    changeCurrentNum: function() {
      const rnd = Math.floor(Math.random() * this.numList.length);
      this.currentNum = this.numList[rnd];
      this.numStateFlag[this.currentNum] = true;
      this.numList.splice(rnd, 1);
      if (this.numList.length == 0) {
        this.startState = false;
      }
    },
    reset: function() {
      Object.assign(this.$data, this.$options.data());
    }
  }
};
</script>

<style scoped>
.current-num {
  width: 100px;
  height: 100px;
  margin: 40px auto 0;
  text-align: center;
  line-height: 100px;
  font-size: 52px;
  background-color: #fff;
  border-radius: 4px;
}

.area-btn {
  margin-top: 40px;
}

.btn {
  display: block;
  width: 180px;
  height: 40px;
  margin: 0 auto;
  color: #fff;
  border: none;
  border-radius: 4px;
  text-shadow: none;
  box-shadow: 0 3px 6px rgba(0, 0, 0, 0.16);
  background-image: none;
  cursor: pointer;
  outline: none;
  font-size: 16px;
  font-weight: bold;
}

.btn + .btn {
  margin-top: 20px;
}

.btn:hover {
  opacity: 0.9;
  transition: 0.5s all;
}

.btn-start {
  background-color: #3cb5f2;
}

.btn-reset {
  background-color: #ef773b;
}

.container {
  width: 700px;
  margin: 40px auto 0;
}

.number-list {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin-left: -5px;
  padding: 0;
}

.number-list li {
  width: 40px;
  height: 40px;
  margin: 0 0 5px 5px;
  background-color: #fff;
  text-align: center;
  line-height: 40px;
  border-radius: 2px;
  list-style: none;
}

.number-list li.displayed {
  background-color: #ffff99;
}
</style>
