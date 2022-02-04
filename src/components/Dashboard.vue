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
          animation: typing 2s steps(30,end) 1s 1 normal both;
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
      background: linear-gradient(
  120deg, #2980b9, #448cad);
      min-height: 30vh;
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
    }
  }
</style>