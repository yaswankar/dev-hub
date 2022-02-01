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
      <div class="middlePane">
          <div class="sidebar" :style="computeStyle">
              <slot name="sideNav"></slot>
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
        computeStyle() {
            return {
                width: !this.toggle ? '56px' : '180px'
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
        position: relative;
        align-items: center;
        height: 56px;
        background-color: #3f51b5;
        border: 1px solid rgba(156,152,152,.5);
        .bar1, .bar2, .bar3 {
            width: 33px;
            height: 4px;
            background-color: #fff;
            margin: 6px 0;
            transition: 0.4s;
        }
        .hamb-container {
            background: #3f51b5;
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
    .middlePane {
        background: #ffffff;
        height: calc(100vh - 56px);
        .sidebar {
            height: 100%;
            background: #316bae;
            transition: 0.5s all;
        }
    }
}
</style>