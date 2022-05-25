<template>
  <header>
    <transition @before-enter="beforeEnter" @enter="enter" appear>
      <nav>
        <div class="menu">
          <router-link to="/"><p class="logo">Greené</p></router-link>
          <div class="hamburger-menu" @click="toggleLinks">
            <span class="bar"></span>
            <span class="bar"></span>
            <span class="bar"></span>
          </div>
        </div>
        <div
          class="nav-links"
          :class="{ showLinks: isVisible }"
          @click="toggleLinks"
        >
          <ul>
            <router-link to="/"><li>Home</li></router-link>
            <a href="/#products"><li>Products</li></a>
            <router-link to="/blog"><li>Blog</li></router-link>
            <router-link to="/about"><li>About</li></router-link>
          </ul>
        </div>
        <div
          class="auth"
          :class="{ showLinks: isVisible }"
          @click="toggleLinks"
        >
          <router-link to="/sign-up"
            ><button class="sign-up">Sign Up</button></router-link
          >
          <router-link to="/log-in"
            ><button class="log-in">Log In</button></router-link
          >
        </div>
      </nav>
    </transition>
  </header>
</template>

<script>
import { ref } from "@vue/reactivity";
import gsap from "gsap";
export default {
  setup() {
    const isVisible = ref(false);

    const toggleLinks = () => {
      isVisible.value = !isVisible.value;
    };

    const beforeEnter = (el) => {
      el.style.opacity = 0;
      el.style.transform = "translateY(-200px)";
      el.style.transition = "all 150ms ease-out";
    };

    const enter = (el, done) => {
      console.log("is working");
      gsap.to(el, {
        opacity: 1,
        y: 0,
        onComplete: done,
      });
    };

    return { isVisible, toggleLinks, beforeEnter, enter };
  },
};
</script>

<style lang="scss" scoped>
header {
  position: relative;
  top: 0;
  width: 100%;
  @include flex(row, center);
  background: var(--vl-green);

  nav {
    @include flex(column, center);
    width: min(90%, 1450px);

    @include breakpoint(desktop) {
      @include flex(row, space-between);
    }

    .menu {
      width: 100%;
      height: 90px;
      @include flex(row, space-between);

      @include breakpoint(desktop) {
        width: auto;
      }

      .logo {
        font-size: 34px;
        font-weight: weight(bold);
        font-family: var(--primary-ft);
        color: var(--d-green);
      }

      .hamburger-menu {
        width: 34px;
        height: 15px;
        cursor: pointer;

        @include breakpoint(desktop) {
          display: none;
        }

        span {
          display: block;
          background: var(--green);
          height: 3px;
          border-radius: 30px;
        }

        span:nth-child(1) {
          width: 100%;
          margin-bottom: 4px;
        }

        span:nth-child(2) {
          width: 80%;
          margin: 0 0 4px 7px;
        }

        span:nth-child(3) {
          width: 50%;
          margin: 0 0 0 17px;
        }
      }
    }

    .nav-links {
      height: 0;
      visibility: hidden;

      @include breakpoint(desktop) {
        visibility: visible;
        height: auto;
      }

      ul {
        @include flex(column, center);
        width: 100%;

        @include breakpoint(desktop) {
          @include flex(row, space-between);
        }

        li {
          font-family: var(--secondary-ft);
          font-weight: weight(semi-bold);
          font-size: 23px;
          margin: 25px;
          text-align: center;
          color: var(--green);
          cursor: pointer;
        }
      }
    }

    .auth {
      @include flex(column, center);
      visibility: hidden;
      height: 0;

      @include breakpoint(desktop) {
        @include flex(row, space-between);
        visibility: visible;
        height: auto;
      }

      .sign-up {
        margin-top: 20px;
        height: 44px;
        width: 144px;
        border: 1px solid var(--green);
        border-radius: 30px;
        background: var(--green);
        cursor: pointer;

        font-size: 23px;
        font-family: var(--secondary-ft);
        font-weight: weight(semi-bold);
        color: var(--vl-green);

        @include breakpoint(desktop) {
          margin: 0;
        }
      }

      .log-in {
        margin: 10px 0 20px;
        height: 44px;
        border: none;
        background: none;
        cursor: pointer;

        font-size: 23px;
        font-family: var(--secondary-ft);
        font-weight: weight(semi-bold);
        color: var(--green);

        @include breakpoint(desktop) {
          margin: 0 0 0 15px;
        }
      }
    }

    .showLinks {
      visibility: visible;
      height: auto;
    }
  }
}
</style>