<template>
  <div class="home">
    <div class="banner">
      <img src="../../static/images/banner.png" alt="">
    </div>
    <div class="content">
      <div class="steps">
        <div class="item" v-for="item in steps">
          <img :src="item.img" alt="">
          <p class="title">{{item.title}}</p>
        </div>
      </div>
      <p class="stepsText">不是业内每一个大咖都真正懂得趋势运行的结构与共振</p>
      <div class="reason">
        <div class="resonBox">
          <p class="title">你知道自己交易亏钱的真正原因吗?</p>
          <div class="item">
            <div class="left" @mouseover="ground" @mouseout="ground">
              <p>从来没有适合自己的投资原理作指导</br>没有正确的交易理论</br>就不会有正确的交易结果</p>
              <span class="circle"></span>
            </div>
            <div class="right" @mouseover="ground" @mouseout="ground">
              <p>脱离交易本质与行情规律去学习研究交易方法</br>方法一大堆</br>交易徒伤悲</p>
              <span class="circle"></span>
            </div>
          </div>
          <div class="people" :class="{ active: isActive,leave: isLeave }">
            <img class="minCircle" src="../../static/images/circle1.png" alt="">
            <img class="maxCircle" src="../../static/images/circle2.png" alt="">
          </div>
          <div class="item">
            <div class="left" @mouseover="ground" @mouseout="ground">
              <p>对行情变化一般状态的实质不会科学地辩证分析</br>思维僵化 把经验当教条</br>一味机械地生搬硬套</p>
              <span class="circle"></span>
            </div>
            <div class="right" @mouseover="ground" @mouseout="ground">
              <p>缺乏独立思考与自我蜕变的勇气和能力</br>保守偏见 心性浮躁</br>人云亦云 歪理一套</p>
              <span class="circle"></span>
            </div>
          </div>
        </div>
        <div class="question">
          <div class="title">面对上述问题</div>
          <p>你需要经历一场思维上彻底的自我革命</br>如果不革命，或革得不彻底不到位，就很难改变现状</br>赚钱都是有方法的，你交易很苦，说明方法不对</br>交易是简单的东西，我们的方法一学就会，一用就灵</br>交易是复杂的东西，我们不教你，你永远都心累</p>
        </div>
      </div>
      <div class="Skill">
        <div class="title">技能特色</div>
        <div class="skillItem">
          <div class="item" v-for="item in skills">
            <p class="cont">{{item.title}}</p>
            <div class="bottom" :class="item.imgClass">
              <p>{{item.bottomTitle}}</p>
              <span class="redLine"></span>
            </div>
          </div>
        </div>
      </div>
      <div class="founderBox">
        <div class="founder">
          <p>结构共振交易体系创始人</p>
          <div :class="{stepLeftactive: isShow}">
            <div class="stepLeft" v-for="item in founder">
              <span class="leftIcon"></span><span class="text">{{item.text}}</span>
            </div>
          </div>
          <div class="imgBox">
            <img src="../../static/images/founder.png" alt="">
          </div>
        </div>
      </div>
      <div class="courses">
        <div class="title">课程精要</div>
        <div class="term">开启交易智慧的三条途径</div>
        <div class="courseItem">
          <p v-for="item in course">{{item.text}}</p>
        </div>
        <div class="term">捕捉趋势的四大方法</div>
        <div class="method" :class="{active: isCircleShow}">
          <p v-for="item in way">{{item.text}}</p>
        </div>
        <div class="term">创造交易财富的五个秘诀</div>
        <div class="create">
          <p v-for="item in create">
            <span>{{item.text}}</span>
            <span>{{item.text2}}</span>
          </p>        
        </div>   
      </div>
      <div class="founderBox">
        <div class="founder learn">
          <p>学习亮点</p>
          <div class="learn">
            <div class="learnItem" v-for="item in learn">
              <div class="itemIcon" :class="item.name"></div>
              <div class="itemTitle">{{item.title}}</div>
              <div class="itemText">{{item.text}}</div>
              <div class="itemText">{{item.text2}}</div>
            </div>
          </div>
        </div>
      </div>
      <div class="founderBox guarant">
        <div class="founder guarantee">
          <p>品质保障</p>
          <div class="guaranteeBox">
            <div class="guaranteeItem item1">
              <img class="bg" src="../../static/images/bgBefore.png" alt="">
              <img class="before" src="../../static/images/classBefore.png" alt="">
              <img class="classBg" src="../../static/images/classBg.png" alt="">
            </div>
            <div class="guaranteeItem item2">
              <img class="bg" src="../../static/images/bging.png" alt="">
              <img class="Ing" src="../../static/images/classIng.png" alt="">
              <img class="classBg" src="../../static/images/classBg.png" alt="">
            </div>
            <div class="guaranteeItem item3">
              <img class="bg" src="../../static/images/bgAfter.png" alt="">
              <img class="after" src="../../static/images/classAfter.png" alt="">
              <img class="classBg" src="../../static/images/classBg.png" alt="">
            </div>
          </div>
        </div>
        <p class="stepsText">不是业内每一个大咖都真正懂得趋势运行的结构与共振</p>
      </div>
      <div class="founderBox profit">
        <div class="founder">
          <div class="title">仓单见证的不只是盈利</div>
          <p class="title2">它是结构共振交易法接受市场检阅的英勇表现</p>
          <div class="guaranteeBox">
          <swiper :options="swiperOption"  ref="mySwiper">  
            <swiper-slide v-for="(banner, index) in banners" :key="index">
              <img v-if="banner" :src="banner">
            </swiper-slide>
            <div class="swiper-pagination"  slot="pagination"></div>
            <!-- <div class="swiper-button-prev" slot="button-prev"></div>
            <div class="swiper-button-next" slot="button-next"></div> -->
          </swiper>
          </div>
        </div>
        <p class="redText">你也能轻松做到 - 实现这个目标 - 你只负责努力 - 我们成就你的梦想 - 让99%的人们看到你的优秀!</p>
      </div>
      <div class="founderBox serveBox">
        <div class="founder serve">
          <p>增值服务</p>
          <div class="item">
            <div class="itemStep"><img src="../../static/images/add1.png" alt=""/>缴一次学费，享受免费复训</div>
            <div class="itemStep"><img src="../../static/images/add2.png" alt=""/>专享大级别行情交易机会的提示</div>
          </div>
          <div class="item">
            <div class="itemStep"><img src="../../static/images/add3.png" alt=""/>参与精英交易员孵化行动</div>
            <div class="itemStep"><img src="../../static/images/add4.png" alt=""/>培育顶级交易团队，加盟“私募合伙人”计划</div>
          </div>
        </div>
      </div>
      <div class="founderBox goodBox">
        <div class="founder good">
          <p>好东西只分享给懂它的有缘人</p>
          <div class="goodSecondBox" :class="{active: isGood}">
            <div class="goodItem" v-for="item in goods" :class="item.position">
              <div class="item">
                <div>{{item.text}}</div>
                <div class="itemResult">{{item.text2}}</div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="contend">
        <p class="title">比拼谁的交易效果更给力，放下偏见，你会有精彩发现</br>选择我们，已经说明你心明眼亮</br>结构共振的大门就在面前</p>
        <div class="end">
          <img src="../../static/images/end.png" alt="">
          <p class="call"><span class="phone"></span>咨询方式：18637118816</p>
        </div>
      </div>
    </div>
    <div class="goTop" @click='goTop' v-show = 'toTop'>返回顶部</div>  
  </div>
</template>

<script>
import { swiper, swiperSlide } from 'vue-awesome-swiper'
export default {
  name: 'Home',
  components: {  
      swiper,  
      swiperSlide
  },
  data () {
    return {
      steps: [
        {title: '行情波动的走向是有规律的', img: '../../static/images/step1.png'},
        {title: '规律是通过结构与共振来体现的', img: '../../static/images/step2.png'},
        {title: '结构和共振是可以被认知的', img: '../../static/images/step3.png'},
      ],
      skills: [
        {bottomTitle: '15 年投资积淀',title: '15 年来专注于金融期货投资研究与交易，“开仓理想，平仓满意”的生存追求，为我们锻炼出一个正确的投资理念，也锻炼出一个正确的投资策略，同时也锻造 了一个正确的交易体系。我们不但会用正确的理念去指导投资，而且还会运用正确的策略去 规划投资，并通过交易体系去圆满完成投资。',imgClass: 'skill1'},
        {bottomTitle: '11 年技术保障',title: '《时空能量》和《结构共振》是我们历时 5 年自主研发的投资分析与实 盘交易两大决策体系，拥有 100%自主的知识产权。它是历经 11 年超千万量级资金实盘检验 的赚钱方法，已成功实现了从自生盈利模式向自觉盈利模式的跨越。',imgClass: 'skill2'},
        {bottomTitle: '趋势把握高效',title: '时空能量预警中国股市及其股指期货周期波动，成果卓著;定性国际原 油、黄金和螺纹等价格未来总体走势及其运行的周期，屡见奇妙!',imgClass: 'skill3'},
        {bottomTitle: '趋势把握高效',title: '结构共振采用最先进的信息处理方式，盘中第一时间把主力买卖诱发分 时波动与趋势走向的高低点，以数字量化实时展现在行情界面上，投资人只要参照指令进行 交易，高抛低吸不再是“说着容易做着难”!',imgClass: 'skill4'}
      ],
      founder: [
        {text: 'CCTV 证券资讯频道特邀高级讲师'},
        {text: '七禾网融界教育签约讲师'},
        {text: '结构共振交易体系创始人'},
        {text: '时空能量分析体系开拓者,'},
        {text:'擅长股票、股指、期货投机交易'},
        {text: '11 年私募操盘经验，实操资金超千万'},
        {text: '超前预警 08 年、11 年、15 年股市暴跌及运行时间'},
      ],
      course: [
        {text: '1、交易需要科学的原理作指导'},
        {text: '2、交易原理科学性的三大特点'},
        {text: '3、原理在交易过程中的具体应用'},
      ],
      way: [
        {text: '结构定量法'},
        {text: '共振定性法'},
        {text: '能量转化法'},
        {text: '走向描述法'},
      ],
      create: [
        {text: '级别推算是根本', text2: '确保开仓稳准很'},
        {text: '三大结构归一统', text2: '日内单边会跟踪'},
        {text: '结构共振趋势转', text2: '重仓出击要果断'},
        {text: '价格周期内窜动', text2: '咬定筹码不放松'},
        {text: '谦虚谨慎是根本', text2: '止盈止损记在心'},
      ],
      learn: [
        {name: 'simple',title: '简单',text: '散步交流 10 分钟，融会贯通全内容',text2: '真传一句话，假传万卷书'},
        {name: 'easy',title: '轻松',text: '从入门到精通，从小白到大咖',text2: '每日演练1次，5天见证奇迹'},
        {name: 'discount',title: '实惠',text: '10余年交易积淀，专注你的成功',text2: '开仓理想，平仓满意'},
      ],
      goods: [
        {text: '不是理性者', text2: '不传授',position: 'up'},
        {text: '心性浮躁者', text2: '不传授',position: 'down'},
        {text: '急功近利者', text2: '不传授',position: 'up'},
        {text: '学起来感觉复杂的', text2: '不收费',position: 'down'},
        {text: '不适合自己交易风格的', text2: '不传授',position: 'up'},
        {text: '用起来不接地气的', text2: '不传授',position: 'down'},
      ],
      banners: [ '../../static/imgs/img1.png', '../../static/imgs/img2.png', '../../static/imgs/img3.png', '../../static/imgs/img4.png', '../../static/imgs/img5.png', '../../static/imgs/img6.png', '../../static/imgs/img7.png', '../../static/imgs/img8.png', '../../static/imgs/img9.png', '../../static/imgs/img10.png', '../../static/imgs/img11.png', '../../static/imgs/img12.png' ],
      swiperOption: {
        autoplay: 3000,
        observeParents: true,
        direction : 'vertical',
        pagination: '.swiper-pagination',
        paginationClickable: true,
        loop: true,
        direction: 'vertical',
        grabCursor: true,
        autoHeight: true,
        observeParents: true,
        // prevButton:'.swiper-button-prev',
        // nextButton:'.swiper-button-next',
        onSlideChangeEnd: swiper => {
          this.page = swiper.realIndex + 1
          this.index = swiper.realIndex
        }
      },
      isActive: false,
      isLeave: false,
      toTop: false,
      timer: null,
      isShow: false,
      isCircleShow: false,
      isGood: false,
    }
  },
  mounted() {  
    this.$nextTick(function () {
       window.addEventListener('scroll', this.needToTop);  //滚动事件监听  
    });
  }, 
  methods: {
    ground: function() {
      this.isActive = !this.isActive;
      if(!this.isActive){
        this.isLeave = true
      }else{
        this.isLeave = false        
      }
    },
    goTop: function() {               // 回到顶部方法  
      clearInterval(this.timer);  
      this.timer = setInterval(function() {   
        let curHeight = document.documentElement.scrollTop || document.body.scrollTop;  // 得到当前高度  
        var now = curHeight;  
        var speed = (0 - now) / 7;                              // 随着高度减速  
        speed = speed > 0 ? Math.ceil(speed) : Math.floor(speed);   
        if (curHeight === 0) {                          //当前高度为零,停止这次计时器  
          clearInterval(this.timer);                             // C1  
        }  
        document.documentElement.scrollTop = curHeight + speed;         //直接给高度赋值,会调用needtotop方法  
        document.body.scrollTop = curHeight + speed;                //谷歌的  
        stop = false  ;                               // A     
     }, 30);  
    },  
    needToTop: function() {  
      let curHeight = document.documentElement.scrollTop || document.body.scrollTop;  
      let viewHeight = document.documentElement.clientHeight;
      if (curHeight > 200) {  
        this.toTop = true;                         //赋值是为了按钮的v-show='toTop'  
      }else{  
        this.toTop = false;  
      }  
      if (stop) {                 //STOP  
        clearInterval(this.timer);             //C2  
      }  
      stop = true;
      if(curHeight>2300&&curHeight<3400){
        this.isShow = true;
      }else{
        this.isShow = false;
      }
      if(curHeight>2900&&curHeight<3900){
        this.isCircleShow = true;
      }else{
        this.isCircleShow = false;
      }
      if(curHeight>5900){
        this.isGood = true;
      }else{
        this.isGood = false;
      }
    }  
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style lang="less">
  @import "../less/home.less";
</style>
