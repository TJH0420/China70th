### 前言：谨以此技术文，庆祝中华人民共和国成立70周年！
##### 本文主讲如何绘制五星红旗，涉及CSS3，ES6+等知识。
### 一、CSS3的单位
##### （1）px
- px，全称pixel，就是我们生活工作中说的像素，也是图像的基本采样单位。对于不同的设备，它的图像基本单位是不同的。而我们生活工作中通常所说的显示器分辨率是指桌面设定的分辨率，不是显示器的物理分辨率。总的来说px就是对应我们显示器的分辨率。
##### （2）em
- em是相对单位，相对于当前标签的字体尺寸（补充：浏览器默认的字体尺寸，也就是16px）。
##### （3）rem
- rem和em一样也是相对单位，但是不一样的是rem始终都是相对html根元素。优点是改变根元素就能改变所有使用rem的大小。新中国，新时代，当然兼容性也“新”，IE8以上版本和其他浏览器都已经支持，是做响应式布局的常用选择。
##### （4）重点：vw和vh
- vw和vh是视口单位，就是根据浏览器窗口的大小的单位，不受显示器分辨率的影响，不需要顾虑那么多不同电脑有关分辨率的自适应问题，是不是很开心？跟我在本文中左手右手用起来。
- vw是视口的宽度单位，vh就是视口的高度。
- 和百分比有点一样，1vw表示可视窗口的宽度的百分之一。比如视口宽度是1900px，那么1vw=19px。和百分比不一样的是，vw始终相对于可视窗口的宽度，而百分比和其父元素的宽度有关。（注：关于vw和vh兼容请查阅相关图表）

### 二、Transform
##### （1）此文用到了translate/rotate/scale，但我们不仅仅这些，具体如图：
![](https://user-gold-cdn.xitu.io/2019/9/29/16d7d349e31d6b4b?w=757&h=988&f=png&s=91781)
### 三、如何实现五角星？
##### （1）第一步：新建一个盒子以及伪元素实现三个三角形
```
    .triangle {
      width: 0;
      height: 0;
      border-right: 5vw solid transparent;
      border-left: 5vw solid transparent;
      border-top: 3.5vw solid #ff0;
    }
    .triangle::after,
    .triangle::before {
      content: "";
      width: 0;
      height: 0;
      border-right: 5vw solid transparent;
      border-left: 5vw solid transparent;
      border-top: 3.5vw solid #ff0;
    }
``` 
##### （2）第二步：三个三角形定位到同一位置
```
    .triangle {
      position: relative;
    }
    .triangle::after,
    .triangle::before {
      position: absolute;
      top: -3.5vw;
      left: -5vw;
    }
``` 
##### （3）第三步：伪元素三角形旋转即实现五角星
```
    .triangle::before {
      transform: rotate(70.5deg);
    }
    .triangle::after {
      transform: rotate(-70.5deg);
}
``` 
##### （4）整合后代码
```
    .triangle {
      width: 0; /* 第一步代码 */
      height: 0; /* 第一步代码 */
      border-right: 5vw solid transparent; /* 第一步代码 */
      border-left: 5vw solid transparent; /* 第一步代码 */
      border-top: 3.5vw solid #ff0; /* 第一步代码 */
      position: relative; /* 第二步代码 */
    }
    .triangle::after,
    .triangle::before {
      content: ""; /* 第一步代码 */
      width: 0; /* 第一步代码 */
      height: 0; /* 第一步代码 */
      border-right: 5vw solid transparent; /* 第一步代码 */
      border-left: 5vw solid transparent; /* 第一步代码 */
      border-top: 3.5vw solid #ff0; /* 第一步代码 */
      position: absolute; /* 第二步代码 */
      top: -3.5vw; /* 第二步代码 */
      left: -5vw; /* 第二步代码 */
    }
    .triangle::before {
      transform: rotate(70.5deg); /* 第三步代码 */
    }
    .triangle::after {
      transform: rotate(-70.5deg); /* 第三步代码 */
    }
``` 
### 四、如何实现国旗？
##### （1）第一步：新增四个已实现五角星盒子
```
    <div class="China-flag">
        <div class="flag-star"></div>
        <div class="flag-star"></div>
        <div class="flag-star"></div>
        <div class="flag-star"></div>
        <div class="flag-star"></div>
    </div>
``` 
##### （2）第二步：伪类结合使用transform技术定位五角星的正确位置
```
    .flag-star:nth-child(1) {
      transform: translate(3.5vw, 7vw) scale(0.9);
    }
``` 
##### （3）整合后代码
```
    .China-flag {
      margin: 5vw auto 2vw auto;
      width: 51.2vw;
      height: 34.1vw;
      background: #f00;
    }
    .flag-star,
    .flag-star::before,
    .flag-star::after
     {
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
      transform: rotate(70.5deg);
    }
    .flag-star::before {
      transform: rotate(-70.5deg);
    }
    .flag-star:nth-child(1) {
      transform: translate(3.5vw, 7vw) scale(0.9);
    }
    .flag-star:nth-child(2) {
      transform: translate(11vw, -2vw) scale(0.33) rotate(-45deg);
    }
    .flag-star:nth-child(3) {
      transform: translate(15vw, -2vw) scale(0.33) rotate(45deg);
    }
    .flag-star:nth-child(4) {
      transform: translate(15vw, 0px) scale(0.33);
    }
    .flag-star:nth-child(5) {
      transform: translate(11vw, 0px) scale(0.33) rotate(-45deg);
    }
``` 
### 五、如何实现多行祝福语，一个一个字展示。
##### （1）HTML结构和数据结构
```
    <div class="China-blessing" v-for="(item,index) in blessingObj" :key="index">
        <span v-for="(item,index) in item" :key="index">{{item}}</span>
    </div>
``` 
```
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
``` 
```
    //假设后端返回的数据如下
    const blessingObj = {
        first: ["我","爱","你","，","中","华","人","民","共","和","国"],
        second: ["此","生","无","悔","入","华","夏","，","来","世","还","做","中","国","人"],
        third: ["微","信","公","众","号","“","黑","叔","说","前","端","”"],
        fourth: ["谨","以","此","技","术","文","献","礼","新","中","国","成","立","70","年"]
    };
``` 
##### （2）初级版实现
```
      let i = 0;
      blessingObj.first.forEach(ele => {
        const _this = this;
        setTimeout(() => {
          _this.blessingObj.first.push(ele);
        }, 200 * i);
        i++;
      });
      blessingObj.second.forEach(ele => {
        const _this = this;
        setTimeout(() => {
          _this.blessingObj.second.push(ele);
        }, 200 * i);
        i++;
      });
      blessingObj.third.forEach(ele => {
        const _this = this;
        setTimeout(() => {
          _this.blessingObj.third.push(ele);
        }, 200 * i);
        i++;
      });
      blessingObj.fourth.forEach(ele => {
        const _this = this;
        setTimeout(() => {
          _this.blessingObj.fourth.push(ele);
        }, 200 * i);
        i++;
      });
``` 
##### （2）中级版实现
```
      let sleep = step => new Promise(resolve => setTimeout(() => resolve(), step))
      ;(async function(param) {
        let _this=param;
        for await (let key of Object.keys(blessingObj)) {
          let __this=_this;
          for await (let value of blessingObj[key]) {
            let ___this=__this;
            await sleep(888)
            ___this.blessingObj[key].push(value)
          }
        }
      })(this)
``` 
##### （3）高级版实现
```
      let i = 0;
      Object.keys(blessingObj).forEach(key => {
        blessingObj[key].forEach(value => {
          setTimeout(() => {
            this.blessingObj[key].push(value);
          }, 168 * i++);
        });
      });
``` 
### 六、效果图
![](https://user-gold-cdn.xitu.io/2019/9/30/16d7dc15b5809d37?w=1074&h=848&f=png&s=47905)
### 七、下期预告：《黑叔说前端》（四）
### 八、代码人生
#### 我将会持续更新，敬请期待。
#### 欢迎扫描二维码关注噢！
![](https://user-gold-cdn.xitu.io/2019/8/10/16c7bd6bce08f303?w=291&h=276&f=png&s=37957)