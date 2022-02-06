<template>
  <main-layout @toggleSidePane="setSidePaneFlag">
      <div slot="sideNav">
        <sidebar :expanded="expanded"/>
      </div>
      <div slot="mainContent" class="main-content">
          <div class="img-container">
            <div class="img-content">
              <h1>Learn Vuejs, Javascript {{'&'}} More</h1>
              <h3 class="typed-out">Learn How To Build Websites {{'&'}} Apps</h3>
              <button class="tour">Take a Tour</button>
            </div>
          </div>
          <div class="section-two">
            <div class="capIcon">
              <div class="capHead"></div>
              <div class="capBottom"></div>
            </div>
            <div class="info-row">
              <div class="info-div">
                <div class="icon-wrapper">
                  <i class="fas fa-video icon-20" alt="video"></i>
                </div>
                <div class="context">
                  <div class="text-one">100+ Online courses</div> 
                  <div class="text-two">Enjoy a variety of fresh topics</div>
                </div>
              </div>
              <div class="info-div">
                <div class="icon-wrapper">
                  <i class="fas fa-certificate icon-20" alt="video"></i>
                </div>
                <div class="context">
                  <div class="text-one">Expert Instruction</div> 
                  <div class="text-two">Find the right instructor for you</div>
                </div>
              </div>
              <div class="info-div">
                <div class="icon-wrapper">
                  <i class="fas fa-infinity icon-20" alt="video"></i>
                </div>
                <div class="context">
                  <div class="text-one">Lifetime access</div> 
                  <div class="text-two">Learn on your schedule</div>
                </div>
              </div>
            </div>
          </div>
          <div class="section-three">
            <div class="sect-one">
              <h1>1</h1>
              <div class="content">
                <h2>Easy to search the topic you want to learn</h2>
                <p>Dev Hub is a collection of many resources. Learn and widen your knowledge dimensions</p>
              </div>
            </div>
            <div class="sect-two">
              <h1>2</h1>
              <div class="content">
                <h2>Join us to help share knowledge to the Community</h2>
                <p>We have an enthusiastic and responsible team from many companies <br/> and corporations with many years of experience. <br/> Join us to grow together.</p>
              </div>
            </div>
            <div class="sect-three">
              <h1>3</h1>
              <div class="content">
                <h2>Dev Hub made easy for users to achieve the desired skills</h2>
                <p>Dev Hub system is meticulously built to enhance the interest of students.<br/> It provides an authentic and easy experience to gain knowledge.</p>
              </div>
            </div>
          </div>
          <div class="section-four">
            <div class="boxer">
              <div class="box-plate"></div>
              <div class="container-box">
                <img class="vue" src="../assets/vue.png" alt="">
                <img class="react" src="../assets/react.png" alt="">
                <img class="js" src="../assets/js.png" alt="">
              </div>
            </div>
          </div>
      </div>
    </main-layout>
</template>

<script>
import MainLayout from '@/components/layouts/MainLayout';
import Sidebar from './layoutComponents/Sidebar.vue';
export default {
    data() {
        return {
            expanded: false
        }
    },
    components: {
        MainLayout,
        Sidebar
    },
    methods: {
        setSidePaneFlag(val) {
            this.expanded = val;
        }
    }
}
</script>

<style lang="scss" scoped>
  .main-content {
    .img-container {
      height: 60vh;
      background-size: cover;
      background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('../assets/elearningBg.jpg');
      background-position: 65% 50%;
      background-attachment: fixed;
      .img-content {
        color: white;
        margin: calc(30vh - 120px) 10%;
        height: auto;
        position: absolute;
        text-align: left;
        @keyframes typing {
          from { width: 0 }
          to { width: 100% }
        }
        .typed-out {
          overflow: hidden;
          white-space: nowrap;
          animation: typing 3s steps(30,end) 1s infinite normal both;
        }
        .tour {
          color: #fff;
          background-color: #3885a8;
          margin-top: 10px;
          padding: 6px 16px;
          font-size: 16px;
          position: relative;
          min-width: 64px;
          box-sizing: border-box;
          font-weight: 500;
          border-radius: 4px;
          border: none;
          outline: none;
          &:after {
            content: "";
            background: #3885a8;
            display: block;
            position: absolute;
            padding-top: 30%;
            padding-left: 100%;
            margin-left: -10px!important;
            margin-top: -25%;
            opacity: 0;
            transition: all 0.8s
          }
          &:active::after {
            padding: 0;
            margin: 0;
            opacity: 1;
            transition: 0s
          }
        }
      }
    }
    .section-two {
        color: white;
        position: relative;
        background: #2980b9;
        min-height: 25vh;
        height: auto;
        .capIcon {
            position: absolute;
            top: 50px;
            left: 10%;
            .capHead {
            width:60px;
            height:60px;
            transform:rotate(45deg);
            background-color:#000;
            }
            .capBottom {
            width: 80px;
            height: 10px;
            margin-top: -9px;
            margin-left: 14px;
            transform: rotate(-45deg);
            background-color: #000;
            }
        }
        .info-row {
        display: flex;
        justify-content: space-evenly;
        position: relative;
        top: 70px;
        left: 22%;
        width: 78%;
        .info-div {
            display: flex;
            .icon-wrapper {
            border: 2px solid #ffffff;
            background: #015981;
            border-radius: 1em;
            max-height: 40px;
            }
            .icon-20 {
            font-size: 20px;
            padding: 10px;
            }
            .context {
            margin-left: 10px;
            text-align: left;
            .text-one {
                font-weight: 600;
            }
            .text-two {
                font-size: 15px;
            }
            }
        }
        }
        .sep-one {
            position: absolute;
            left: 0;
            top: 18vh;
            background: white;
            fill: #2980b9;
        }
    }
    .section-three {
      padding: 56px 40px 20px 40px;
      position: relative;
      background: #ffffff;
      .sect-one, .sect-two, .sect-three {
        display: flex;
        text-align: left;
        .content {
          margin-left: 20px;
          margin-bottom: 30px;
          h3 {
            color: #015981;
          }
          p {
            font-weight: 500;
          }
        }
      }
      .sect-one, .sect-three {
        justify-content: flex-start;
      }
      .sect-two {
        justify-content: flex-end;
      }
    }
    .section-four {
      height: auto;
      padding: 10px 20px;
      position: relative;
      background: #ffffff;
      .boxer {
        width: 60%;
        margin: 0 auto;
        .box-plate {
          background: #3885a8;
          position: relative;
          transform: rotate(-10deg);
          border: 2px solid #4d4d4d;
          height: 50px;
          top: 20px;
          left: -10px;
        }
        .container-box {
          margin-top: 100px;
          border: 2px solid #4d4d4d;
          height: 400px;
          text-align: left;
          position: relative;
          &::before {
            content: '';
            position: absolute;
            background: #04ACFF;
            width: 100%;
            bottom: 0;
            animation: wipe 5s cubic-bezier(.2,.6,.8,.4) infinite alternate;
          }
          img {
            width: 50px;
            height: 50px;
            position: absolute;
          }
          .vue {
            animation: vueanime 5s linear 2s infinite alternate;
          }
          .react {
            animation: reactanime 5s linear 2s infinite alternate;
          }
          .js {
            animation: jsanime 5s linear 2s infinite alternate;
          }
          @keyframes vueanime {
            0%   {transform: rotate(-45deg); left:100px; top:0px;}
            25%  {transform: rotate(-90deg); left:calc(100% - 50px); top:100px;}
            50%  {transform: rotate(-135deg); left:200px; top:calc(100% - 50px);}
            75%  {transform: rotate(-180deg); left:0px; top:200px;}
            100% {transform: rotate(-225deg); left:100px; top:0px;}
          }
          @keyframes reactanime {
            0%   {transform: rotate(-45deg); left:0px; top:200px;}
            20%  {transform: rotate(-90deg); left:200px; top:0px;}
            40%  {transform: rotate(-135deg); left:calc(100% - 50px); top:300px;}
            60%  {transform: rotate(-180deg); left:calc(20%); top:calc(100% - 50px);}
            80% {transform: rotate(-225deg); left:0px; top:200px;}
            100% {transform: rotate(-270deg); left:calc(40%); top:0px;}
          }
          @keyframes jsanime {
            0%   {transform: rotate(-45deg); left:calc(100% - 50px); top:calc(100% - 50px);}
            20%  {transform: rotate(-90deg); left:calc(60%); top:calc(100% - 50px);}
            40%  {transform: rotate(-135deg); left:100px; top:350px;}
            60%  {transform: rotate(-180deg); left:calc(100% - 100px); top: 50px;}
            80% {transform: rotate(-225deg); left:calc(100% - 50px); top:100px;}
            100% {transform: rotate(-270deg); left:calc(50%); top:calc(50%);}
          }
          @keyframes wipe {
            0% {
              height: 0;
            }
            100% {
              height: 90%;
            }
          }
        }
      }
      
    }
}
</style>