<template>
  <div id="app">
    <main-layout @toggleSidePane="setSidePaneFlag">
      <div slot="sideNav" class="sideNav">
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
  .sideNav {
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
            background: #DA312515;
            border-radius: 5%;
            width: 100%;
            height: 100%;
            .showText {
              color: #DA3125 !important;
            }
            i {
              color: #DA3125 !important;
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
}
</style>
