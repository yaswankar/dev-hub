<template>
  <div class="main-layout">
      <slot name="header">
          <div class="menu-bar">
              <button :class="{'hamb-container change': toggle, 'hamb-container': !toggle }" @click="toggleHamburger">
                <div class="bar1"></div>
                <div class="bar2"></div>
                <div class="bar3"></div>
              </button>
              <button class="login">
                  <i class="fas fa-key"></i>
                  <span>Login</span>
              </button>
              <button class="sign-up">
                  <span>Sign Up</span>
              </button>
          </div>
      </slot>
      <div class="body">
          <div class="sidebar" :style="computeSidebarStyle">
              <slot name="sideNav"></slot>
          </div>
          <div class="content-section" :style="computeCenterStyle">
              <slot name="mainContent"></slot>
          </div>
      </div>
  </div>
</template>

<script>
export default {
    data() {
        return {
            toggle: false
        };
    },
    computed: {
        computeSidebarStyle() {
            return {
                width: !this.toggle ? '56px' : '180px'
            }
        },
        computeCenterStyle() {
            return {
                width: !this.toggle ? 'calc(100% - 56px)' : 'calc(100% - 180px)' 
            }
        }
    },
    methods: {
        toggleHamburger() {
            this.toggle = !this.toggle;
            this.$emit('toggleSidePane', this.toggle);
        }
    }
}
</script>

<style lang="scss">
.main-layout {
    .menu-bar {
        display: flex;
        position: sticky;
        align-items: center;
        height: 56px;
        background: linear-gradient(
  120deg, #2980b9, #448cad);;
        border: 1px solid rgba(156,152,152,.5);
        .bar1, .bar2, .bar3 {
            width: 33px;
            height: 4px;
            background-color: #fff;
            margin: 6px 0;
            transition: 0.4s;
        }
        .hamb-container {
            background: transparent;
            border: none;
            outline: none;
            margin-left: 6px;
        }
        .change {
            .bar1 {
                -webkit-transform: rotate(-45deg) translate(-7px, 6px);
                transform: rotate(-45deg) translate(-7px, 6px);
            }
            .bar2 {opacity: 0;}
            .bar3 {
                -webkit-transform: rotate(45deg) translate(-8px, -8px);
                transform: rotate(45deg) translate(-8px, -8px);
            }
        }
        .login, .sign-up {
            width: 90px;
            height: 30px;
            position: absolute;
        }
        .login {
            right: 100px;
            span {
                margin-left: 10px;
            }
        }
        .sign-up {
            right: 5px
        }
    }
    .body {
        background: #ffffff;
        height: calc(100vh - 56px);
        display: flex;
        .sidebar {
            height: 100%;
            background: #ffffff;
            transition: width 180ms ease-in-out;
            border: 1px solid rgba(156,152,152,.5);
        }
        .content-section {
            max-height: 100%;
            overflow: auto;
            transition: width 180ms ease-in-out;
        }
    }
}
</style>