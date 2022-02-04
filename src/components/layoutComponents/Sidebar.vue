<template>
  <div class="side-nav">
        <ul>
          <li :class="{'nav-btn-open': this.getExpanded, 'nav-btn': !this.getExpanded, 'active': this.activeOption.dashboard}">
            <a @click="selectItem('dashboard')">
              <i class="fas fa-home nav-icon"></i>
              <div :class="{'showText': this.getExpanded, 'hideText': !this.getExpanded}">Dashboard</div>
            </a>
          </li>
          <li :class="{'nav-btn-open': this.getExpanded, 'nav-btn': !this.getExpanded, 'active': this.activeOption.courses}">
            <a @click="selectItem('courses')">
              <i class="fas fa-list nav-icon"></i>
              <div :class="{'showText': this.getExpanded, 'hideText': !this.getExpanded}">Courses</div>
            </a>
          </li>
          <li :class="{'nav-btn-open': this.getExpanded, 'nav-btn': !this.getExpanded, 'active': this.activeOption.about}">
            <a @click="selectItem('about')">
              <i class="fas fa-info-circle nav-icon"></i>
              <div :class="{'showText': this.getExpanded, 'hideText': !this.getExpanded}">About</div>
            </a>
          </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Sidebar',
    data() {
        return {
            activeOption: {
                dashboard: true,
                courses: false,
                about: false
            }
        }
    },
    props: {
        expanded: {
            type: Boolean,
            default: false
        }
    },
    computed: {
        getExpanded() {
            return this.expanded;
        }
    },
    methods: {
        selectItem(key) {
            Object.keys(this.activeOption).forEach(ky => this.activeOption[ky] = false);
            this.activeOption[key] = true;
        },
    }
}
</script>

<style lang="scss" scoped>
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
</style>