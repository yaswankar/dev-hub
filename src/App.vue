<template>
  <div id="app">
    <main-layout @toggleSidePane="setSidePaneFlag">
      <div slot="sideNav" class="side-nav">
        <ul>
          <li :class="{'nav-btn-open': this.expanded, 'nav-btn': !this.expanded, 'active': this.activeOption.dashboard}">
            <a @click="selectItem('dashboard')">
              <i class="fas fa-home nav-icon"></i>
              <div :class="{'showText': this.expanded, 'hideText': !this.expanded}">Dashboard</div>
            </a>
          </li>
          <li :class="{'nav-btn-open': this.expanded, 'nav-btn': !this.expanded, 'active': this.activeOption.courses}">
            <a @click="selectItem('courses')">
              <i class="fas fa-list nav-icon"></i>
              <div :class="{'showText': this.expanded, 'hideText': !this.expanded}">Courses</div>
            </a>
          </li>
          <li :class="{'nav-btn-open': this.expanded, 'nav-btn': !this.expanded, 'active': this.activeOption.about}">
            <a @click="selectItem('about')">
              <i class="fas fa-info-circle nav-icon"></i>
              <div :class="{'showText': this.expanded, 'hideText': !this.expanded}">About</div>
            </a>
          </li>
        </ul>
      </div>
      <div slot="mainContent" class="main-content">
          <div class="img-container">
            <div class="img-content">
              <h1>Learn Vuejs, Javascript {{'&'}} More</h1>
              <h3 class="typed-out">Learn How To Build Websites {{'&'}} Apps</h3>
              <button class="tour">Take a Tour</button>
            </div>
          </div>
          <div class="section-two"></div>
      </div>
    </main-layout>
  </div>
</template>

<script>
import MainLayout from '@/components/layouts/MainLayout'
export default {
  data() {
    return {
      expanded: false,
      activeOption: {
        dashboard: true,
        courses: false,
        about: false
      }
    }
  },
  components: {
    MainLayout
  },
  methods: {
    selectItem(key) {
      Object.keys(this.activeOption).forEach(ky => this.activeOption[ky] = false);
      this.activeOption[key] = true;
    },
    setSidePaneFlag(val) {
      this.expanded = val;
    }
  }
}
</script>
<style lang="scss">
body {
  margin: 0;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  .side-nav {
    display: flex;
    flex-direction: column;
    padding: 15px 0;
    ul {
      list-style: none;
      padding: 0;
      margin: 0;
      .nav-btn, .nav-btn-open {
        position: relative;
        text-align: left;
        background: transparent;
        display: flex;
        height: 40px;
        padding: 10px 15px;
        box-sizing: border-box;
        a {
          display: flex;
          transition: width 200ms ease-in-out;
          text-decoration: none;
          width: 100%;
          height: 100%;
          .nav-icon {
            color: gray;
            font-size: 20px;
          }
          .showText {
            margin-left: 10px;
            font-weight: 600;
            color: gray;
            opacity: 1;
            display: block;
          }
          .hideText {
            opacity: 0;
            width: 0;
            transition: width 200ms ease-in-out;
            display: none;
          }
        }
      }
      .active {
            background: #2980b915;
            border-radius: 5%;
            width: 100%;
            height: 100%;
            .showText {
              color: #2980b9 !important;
            }
            i {
              color: #2980b9 !important;
            }
            &::before {
              content: "";
              height: 100%;
              width: 3px;
              color: rebeccapurple;
              position: absolute;
            }
      }
      .nav-btn {
        justify-content: center;
      }
      .nav-btn-open {
        justify-content: flex-start;
      }
    }
  }
  .main-content {
    .img-container {
      height: 60vh;
      background-size: cover;
      background-image: linear-gradient(rgba(0, 0, 0, 0.4), rgba(0, 0, 0, 0.4)), url('./assets/elearningBg.jpg');
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
    }
  }
}
</style>
