<template>
  <div class="China">
    <div class="China-flag">
      <div class="flag-star"></div>
      <div class="flag-star"></div>
      <div class="flag-star"></div>
      <div class="flag-star"></div>
      <div class="flag-star"></div>
    </div>
    <div class="China-blessing" v-for="(item,index) in blessingObj" :key="index">
      <span v-for="(item,index) in item" :key="index">{{item}}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "ChinaSeventy",
  props: {
    msg: String
  },
  data() {
    return {
      blessingObj: {
        first: [],
        second: [],
        third: [],
        fourth: []
      }
    };
  },
  created() {
    this.setWorldHandler();
  },
  methods: {
    setWorldHandler() {
      const blessingObj = {
        first: [
          "我",
          "爱",
          "你",
          "，",
          "中",
          "华",
          "人",
          "民",
          "共",
          "和",
          "国"
        ],
        second: [
          "此",
          "生",
          "无",
          "悔",
          "入",
          "华",
          "夏",
          "，",
          "来",
          "世",
          "还",
          "做",
          "中",
          "国",
          "人"
        ],
        third: [
          "微",
          "信",
          "公",
          "众",
          "号",
          "“",
          "黑",
          "叔",
          "说",
          "前",
          "端",
          "”"
        ],
        fourth: [
          "谨",
          "以",
          "此",
          "技",
          "术",
          "文",
          "献",
          "礼",
          "新",
          "中",
          "国",
          "成",
          "立",
          "70",
          "年"
        ]
      };

      // 高级版代码（初级版与中级版本智慧的结晶）
      let i = 0;
      Object.keys(blessingObj).forEach(key => {
        blessingObj[key].forEach(value => {
          setTimeout(() => {
            this.blessingObj[key].push(value);
          }, 168 * i++);
        });
      });

      // 中级版代码
      // let sleep = step => new Promise(resolve => setTimeout(() => resolve(), step))
      // ;(async function(param) {
      //   let _this=param;
      //   for await (let key of Object.keys(blessingObj)) {
      //     let __this=_this;
      //     for await (let value of blessingObj[key]) {
      //       let ___this=__this;
      //       await sleep(888)
      //       ___this.blessingObj[key].push(value)
      //     }
      //   }
      // })(this)

      // 初级版代码
      // let i = 0;
      // blessingObj.first.forEach(ele => {
      //   const _this = this;
      //   setTimeout(() => {
      //     _this.blessingObj.first.push(ele);
      //   }, 200 * i);
      //   i++;
      // });
      // blessingObj.second.forEach(ele => {
      //   const _this = this;
      //   setTimeout(() => {
      //     _this.blessingObj.second.push(ele);
      //   }, 200 * i);
      //   i++;
      // });
      // blessingObj.third.forEach(ele => {
      //   const _this = this;
      //   setTimeout(() => {
      //     _this.blessingObj.third.push(ele);
      //   }, 200 * i);
      //   i++;
      // });
      // blessingObj.fourth.forEach(ele => {
      //   const _this = this;
      //   setTimeout(() => {
      //     _this.blessingObj.fourth.push(ele);
      //   }, 200 * i);
      //   i++;
      // });

    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.tri {
  width: 0;
  height: 0;
  border-right: 5vw solid transparent;
  border-left: 5vw solid transparent;
  border-top: 3.5vw solid #ff0;
}
.tri::after,
.tri::before {
  width: 0;
  height: 0;
  border-right: 5vw solid transparent;
  border-left: 5vw solid transparent;
  border-top: 3.5vw solid #ff0;
}
.tri::before {
  transform: rotate(70.5deg);
}
.tri::after {
  transform: rotate(-70.5deg);
}

.China-flag {
  margin: 5vw auto 2vw auto;
  width: 51.2vw;
  height: 34.1vw;
  background: #f00;
}

.flag-star,
.flag-star::before,
.flag-star::after {
  width: 0;
  height: 0;
  border-right: 5vw solid transparent;
  border-left: 5vw solid transparent;
  border-top: 3.5vw solid #ff0;
}

.flag-star {
  position: relative;
}

.flag-star::after,
.flag-star::before {
  position: absolute;
  content: "";
  top: -3.5vw;
  left: -5vw;
}

.flag-star::after {
  -webkit-transform: rotate(70.5deg);
  -moz-transform: rotate(70.5deg);
  -ms-transform: rotate(70.5deg);
  -o-transform: rotate(70.5deg);
  transform: rotate(70.5deg);
}

.flag-star::before {
  -webkit-transform: rotate(-70.5deg);
  -moz-transform: rotate(-70.5deg);
  -ms-transform: rotate(-70.5deg);
  -o-transform: rotate(-70.5deg);
  transform: rotate(-70.5deg);
}

.flag-star:nth-child(1) {
  -webkit-transform: translate(3.5vw, 7vw) scale(0.9);
  -moz-transform: translate(3.5vw, 7vw) scale(0.9);
  -ms-transform: translate(3.5vw, 7vw) scale(0.9);
  -o-transform: translate(3.5vw, 7vw) scale(0.9);
  transform: translate(3.5vw, 7vw) scale(0.9);
}

.flag-star:nth-child(2) {
  -webkit-transform: translate(11vw, -2vw) scale(0.33) rotate(-45deg);
  -moz-transform: translate(11vw, -2vw) scale(0.33) rotate(-45deg);
  -ms-transform: translate(11vw, -2vw) scale(0.33) rotate(-45deg);
  -o-transform: translate(11vw, -2vw) scale(0.33) rotate(-45deg);
  transform: translate(11vw, -2vw) scale(0.33) rotate(-45deg);
}

.flag-star:nth-child(3) {
  -webkit-transform: translate(15vw, -2vw) scale(0.33) rotate(45deg);
  -moz-transform: translate(15vw, -2vw) scale(0.33) rotate(45deg);
  -ms-transform: translate(15vw, -2vw) scale(0.33) rotate(45deg);
  -o-transform: translate(15vw, -2vw) scale(0.33) rotate(45deg);
  transform: translate(15vw, -2vw) scale(0.33) rotate(45deg);
}

.flag-star:nth-child(4) {
  -webkit-transform: translate(15vw, 0px) scale(0.33);
  -moz-transform: translate(15vw, 0px) scale(0.33);
  -ms-transform: translate(15vw, 0px) scale(0.33);
  -o-transform: translate(15vw, 0px) scale(0.33);
  transform: translate(15vw, 0px) scale(0.33);
}

.flag-star:nth-child(5) {
  -webkit-transform: translate(11vw, 0px) scale(0.33) rotate(-45deg);
  -moz-transform: translate(11vw, 0px) scale(0.33) rotate(-45deg);
  -ms-transform: translate(11vw, 0px) scale(0.33) rotate(-45deg);
  -o-transform: translate(11vw, 0px) scale(0.33) rotate(-45deg);
  transform: translate(11vw, 0px) scale(0.33) rotate(-45deg);
}

.China-blessing {
  -webkit-transform: scale(0.33);
  -moz-transform: scale(0.33);
  -ms-transform: scale(0.33);
  -o-transform: scale(0.33);
  transform: scale(0.33);
  font-weight: 900;
  font-size: 5vw;
  color: #f00;
}
@keyframes show {
  0% {
    opacity: 0;
  }
  100% {
    opacity: 1;
  }
}
.China-blessing span {
  animation: show 0.2s both;
}
</style>
