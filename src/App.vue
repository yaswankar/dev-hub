<template>
  <div id="app">
    <main-layout @toggleSidePane="setSidePaneFlag">
      <div slot="sideNav" class="sideNav">
        <button class="nav-btn">
          <i class="fas fa-home nav-icon"></i>
          <span v-if="this.expanded">Dashboard</span>
        </button>
        <button class="nav-btn">
          <i class="fas fa-list nav-icon"></i>
          <span v-if="this.expanded">Courses</span>
        </button>
        <button class="nav-btn">
          <i class="fas fa-info-circle nav-icon"></i>
          <span v-if="this.expanded">About</span>
        </button>
      </div>
    </main-layout>
  </div>
</template>

<script>
import MainLayout from '@/components/layouts/MainLayout'
export default {
  data() {
    return {
      expanded: false
    }
  },
  components: {
    MainLayout
  },
  methods: {
    setSidePaneFlag(val) {
      if(val) {
        setTimeout(() => {
          this.expanded = val;
        }, 180);
      } else this.expanded = val;
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
    padding: 10px;
    .nav-btn {
      margin-top: 20px;
      text-align: left;
      background: transparent;
      border: none;
      outline: none;
      .nav-icon {
        color: #ffffff;
        font-size: 20px;
      }
      span {
        margin-left: 10px;
        font-weight: 600;
        color: #ffffff;
      }
    }
  }
}
</style>
