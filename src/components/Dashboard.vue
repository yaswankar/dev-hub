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
            <svg viewBox="0 0 1430 140" class="sep-one" xmlns="http://www.w3.org/2000/svg"><path d="M1440 0v59.969c-65.287-39.594-188.865-55.343-370.736-47.248C766 26.221 627.87 140 277 140 171.698 140 79.365 124.417 0 93.25V0h1440z"></path></svg>
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
                <h2>Dev Hub users easy to achieve the desired skills</h2>
                <p>Dev Hub system is meticulously built to enhance the interest of students.<br/> It provides an authentic and easy experience to gain knowledge.</p>
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
      padding: 20px 40px;
      margin-top: 36px;
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
}
</style>