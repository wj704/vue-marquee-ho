<style>
  .marquee-box {
    height: 50px;
    line-height: 50px;
    color: #000;
    font-size: 24px;
    background-size: 24px 24px;
  }
  .marquee-content{
    overflow: hidden;
    width:100%
  }
  .marquee-content p{
    display: inline-block;
    white-space: nowrap;
    margin: 0;
    font-size: 0;
  }
  .marquee-content span{
    display: inline-block;
    white-space: nowrap;
    padding-right: 40px;
    font-size: 24px;
  }

  .quick{
    -webkit-animation: marquee 5s linear infinite;
    animation: marquee 5s linear infinite;
  }
  .middle{
    -webkit-animation: marquee 8s linear infinite;
    animation: marquee 8s linear infinite;
  }
  .slow{
    -webkit-animation: marquee 25s linear infinite;
    animation: marquee 25s linear infinite;
  }
  @-webkit-keyframes marquee {
    0%  { -webkit-transform: translate3d(0,0,0); }
    100% { -webkit-transform: translate3d(-50%,0,0); }
  }
  @keyframes marquee {
    0%  { transform: translateX(0); }
    100% { transform: translateX(-50%);}
  }
</style>

<template>
  <div class="marquee-box">
    <div class="marquee-content" ref="out">
      <p :class="run?speed:''">
        <span class="text1" ref="in" >{{content}}</span>
        <span class="text2" v-if="showtwo||run">{{content}}</span>
      </p>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'VueMarquee',
    data (){
      return{
        run: false,
        pWidth: '',
      }
    },
    props: {
      content: {
        default: "暂无内容",
        type: String
      },
      speed: {
        default: 'middle',
        type: String
      },
      showtwo: {
        default: true
      }
    },
    watch: {
      content (){
        var _this = this;
        setTimeout(()=>{
          // let out = document.getElementById(_this.pid.out).clientWidth;
          // let _in = document.getElementById(_this.pid.in).clientWidth;
          _this.$nextTick(()=>{
            let out = _this.$refs.out.clientWidth;
            let _in = _this.$refs.in.clientWidth;
            _this.pWidth = 2*_in;
            _this.run=_in>out?true:false;
          });
        },0);
      }
    },
    mounted (){
      // let out = document.getElementById(this.pid.out).clientWidth;
      // let _in = document.getElementById(this.pid.in).clientWidth;
      var _this = this;
      this.$nextTick(()=>{
        let out = _this.$refs.out.clientWidth;
        let _in = _this.$refs.in.clientWidth;
        _this.run=_in>out?true:false;
      });
    }
  }
</script>
