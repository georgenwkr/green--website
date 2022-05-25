<template>
  <transition @before-enter="beforeEnter" @enter="enter" appear>
    <div class="error-section">
      <div class="error-container">
        <h2>Sorry, there's no content.</h2>
        <router-link to="/"><button>Return to Home Page</button></router-link>
      </div>
    </div>
  </transition>
</template>

<script>
import gsap from "gsap";
export default {
  setup() {
    const beforeEnter = (el) => {
      el.style.opacity = 0;
      el.style.transform = "translateY(100px)";
      el.style.transition = "all 300ms ease-out";
    };

    const enter = (el, done) => {
      console.log("is workingeh");
      gsap.to(el, {
        opacity: 1,
        y: 0,
        onComplete: done,
      });
    };

    return { beforeEnter, enter };
  },
};
</script>

<style lang="scss">
.error-section {
  width: 100%;
  height: 60vh;

  .error-container {
    width: min(90%, 1450px);
    height: 100%;
    margin: 0 auto;
    @include flex(column, center);

    h2 {
      font-family: var(--primary-ft);
      font-weight: weight(bold);
      color: var(--d-green);
      font-size: 40px;
      letter-spacing: -1px;
      margin: 20px auto;

      @include breakpoint(desktop) {
        font-size: 60px;
      }
    }

    button {
      height: 50px;
      width: 270px;
      border: 1px solid var(--green);
      border-radius: 30px;
      background: var(--green);
      color: var(--vl-green);
      font-family: var(--secondary-ft);
      font-weight: weight(semi-bold);
      font-size: 25px;
      cursor: pointer;

      @include breakpoint(desktop) {
        font-size: 28px;
        height: 54px;
        width: 350px;
      }
    }
  }
}
</style>