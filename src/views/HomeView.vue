<template>
  <transition @before-enter="beforeEnter" @enter="enter" appear>
    <section class="hero-section">
      <div class="hero-container">
        <div class="hero-info">
          <h1>Live a life with added quality</h1>

          <p>
            Enjoy the health and aesthetic benefits of having a beautiful greené
            space.
          </p>

          <router-link to="/buy-products"
            ><button>Buy Products</button></router-link
          >
        </div>
        <div class="hero-image">
          <figure>
            <img src="../assets/hero-image.svg" alt="image of plants" />
          </figure>
        </div>
      </div>
    </section>
  </transition>
  <section class="products-section" id="products">
    <div class="products-container">
      <div class="heading">
        <h2>Products</h2>
      </div>
      <div class="product-items">
        <div class="product">
          <div class="product-image">
            <img src="@/assets/indoor-plant-img.svg" alt="" />
          </div>
          <div class="product-info">
            <h3>Indoor Plants</h3>
            <p>The best household plants for an indoor bliss.</p>
            <router-link to="/indoor-plants"
              ><p class="link">See More</p></router-link
            >
          </div>
        </div>
        <div class="product">
          <div class="product-image">
            <img src="@/assets/outdoor-plant-img.svg" alt="" />
          </div>
          <div class="product-info">
            <h3>Outdoor Plants</h3>
            <p>The best plants for a sensational garden.</p>
            <router-link to="/outdoor-plants"
              ><p class="link">See More</p></router-link
            >
          </div>
        </div>
        <div class="product">
          <div class="product-image">
            <img src="@/assets/flower-seeds-img.svg" alt="" />
          </div>
          <div class="product-info">
            <h3>Flower Seeds</h3>
            <p>Plant and nurture.</p>
            <router-link to="/flower-seeds"
              ><p class="link">See More</p></router-link
            >
          </div>
        </div>
        <div class="product">
          <div class="product-image">
            <img src="@/assets/garden-tools-img.svg" alt="" />
          </div>
          <div class="product-info">
            <h3>Garden Tools</h3>
            <p>All the garden accessories you need.</p>
            <router-link to="/garden-tools"
              ><p class="link">See More</p></router-link
            >
          </div>
        </div>
      </div>
    </div>
  </section>
  <section class="quote-section">
    <div class="quote-container">
      <h3>To plant a garden is to believe in tomorrow</h3>
      <p>— Audrey Hepburn</p>
    </div>
  </section>
  <section class="bestsellers-section">
    <div class="bestsellers-container">
      <div class="heading">
        <h2>Bestsellers</h2>
      </div>
      <div class="bestseller-items">
        <div class="bestseller">
          <img src="../assets/snake-plant-img.svg" alt="snake plant" />
          <h3>Snake Plant</h3>
          <p>N12,999.99</p>
          <button>Add to Cart</button>
        </div>
        <div class="bestseller">
          <img src="../assets/cactus-img.svg" alt="snake plant" />
          <h3>Cactus</h3>
          <p>N10,999.99</p>
          <button>Add to Cart</button>
        </div>
        <div class="bestseller">
          <img src="../assets/parlor-palm-img.svg" alt="snake plant" />
          <h3>Parlor Palm</h3>
          <p>N7,999.99</p>
          <button>Add to Cart</button>
        </div>
      </div>
    </div>
  </section>
  <Newsletter />
</template>

<script>
import Newsletter from "@/components/Newsletter.vue";
import Footer from "@/components/Footer.vue";
import gsap from "gsap";
export default {
  name: "HomeView",
  components: { Newsletter, Footer },
  setup() {
    const beforeEnter = (el) => {
      el.style.opacity = 0;
      el.style.transform = "translateY(200px)";
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

<style lang="scss" scoped>
.hero-section {
  width: min(90%, 1450px);
  height: auto;
  margin: 20px auto;

  @include breakpoint(desktop) {
    margin: 0 auto;
  }

  .hero-container {
    display: grid;
    grid-template-columns: 1fr;
    justify-items: center;

    @include breakpoint(desktop) {
      grid-template-columns: 1fr 1fr;
      max-height: 90vh;
    }

    .hero-info {
      text-align: center;

      @include breakpoint(desktop) {
        text-align: left;
      }

      h1 {
        font-family: var(--primary-ft);
        font-weight: weight(bold);
        color: var(--d-green);
        font-size: 40px;
        letter-spacing: -1px;
        max-width: 300px;
        margin: auto;

        @include breakpoint(desktop) {
          margin: 90px 0 25px;
          font-size: 64px;
          line-height: 78px;
          max-width: 600px;
        }
      }

      p {
        font-family: var(--secondary-ft);
        font-weight: weight(regular);
        color: var(--green);
        font-size: 28px;
        margin-top: 30px;
        max-width: 600px;

        @include breakpoint(desktop) {
          font-size: 30px;
          margin-top: 12px;
          line-height: 1.4;
        }
      }

      button {
        height: 50px;
        width: 180px;
        border: 1px solid var(--green);
        border-radius: 30px;
        background: var(--green);
        color: var(--vl-green);
        font-family: var(--secondary-ft);
        font-weight: weight(semi-bold);
        font-size: 25px;
        margin: 20px auto;
        cursor: pointer;

        @include breakpoint(desktop) {
          font-size: 28px;
          height: 54px;
          width: 240px;
        }
      }
    }

    .hero-image {
      width: 100%;
      max-height: 600px;

      @include breakpoint(desktop) {
        height: 90vh;
      }

      figure {
        width: 100%;
        height: 100%;
        object-fit: contain;

        img {
          width: 100%;
          height: 100%;
          object-fit: contain;
        }
      }
    }
  }
}

.products-section {
  width: 100%;

  .products-container {
    width: min(90%, 900px);
    margin: 100px auto;
    @include flex(column, center);

    .heading {
      font-family: var(--primary-ft);
      color: var(--d-green);
      font-size: 32px;
      font-weight: weight(bold);
      margin: 20px auto;
    }

    .product-items {
      display: grid;
      grid-template-columns: 1fr;
      justify-items: center;
      align-items: center;

      @include breakpoint(tablet) {
        grid-template-columns: repeat(2, 1fr);
        grid-gap: 16px;
      }

      .product {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        text-align: center;
        margin: 20px auto;

        @include breakpoint(tablet) {
          flex-direction: row;
          min-height: 250px;
          min-width: 400px;
          text-align: left;
        }

        .product-image {
          width: 145px;
          object-fit: contain;

          @include breakpoint(tablet) {
            width: 40%;
          }

          img {
            width: 100%;
          }
        }

        .product-info {
          @include breakpoint(tablet) {
            padding-left: 8px;
            width: 60%;
          }
          h3 {
            font-family: var(--primary-ft);
            font-weight: weight(regular);
            font-size: 26px;
            color: var(--d-green);
            margin: 16px auto;
          }

          p {
            font-family: var(--secondary-ft);
            font-size: 22px;
            font-weight: weight(regular);
            color: var(--green);
            margin-bottom: 13px;
          }

          .link {
            font-family: var(--primary-ft);
            font-weight: weight(regular);
            color: var(--d-green);
            font-size: 22px;
            text-decoration: underline;
            cursor: pointer;
          }
        }
      }
    }
  }
}

.quote-section {
  width: 100%;

  .quote-container {
    width: min(90%, 1450px);
    margin: 130px auto;
    // @include flex(column, center);

    h3 {
      font-family: var(--primary-ft);
      font-weight: weight(bold);
      color: var(--d-green);
      letter-spacing: -1px;
      font-size: 32px;
      text-align: center;
      position: relative;

      &::before {
        content: open-quote;
        color: var(--green);
      }

      &::after {
        content: close-quote;
        color: var(--green);
      }

      @include breakpoint(desktop) {
        font-size: 55px;
      }
    }

    p {
      text-align: right;
      margin: 0 auto;
      width: min(90%, 900px);
      font-family: var(--secondary-ft);
      font-weight: weight(regular);
      font-size: 22px;
      color: var(--green);

      @include breakpoint(desktop) {
        font-size: 34px;
      }
    }
  }
}

.bestsellers-section {
  width: 100%;

  .bestsellers-container {
    width: min(90%, 800px);
    margin: 130px auto;
    @include flex(column, center);

    .heading {
      font-family: var(--primary-ft);
      color: var(--d-green);
      font-size: 32px;
      font-weight: weight(bold);
      margin: 20px auto;
    }

    .bestseller-items {
      width: 100%;
      @include flex(row, space-between);
      align-items: flex-end;
      margin: 10px auto;
      overflow: scroll;

      .bestseller {
        margin: 20px 50px;
        @include flex(column, center);
        height: auto;
        min-width: 150px;

        h3 {
          font-size: 27px;
          font-weight: weight(regular);
          font-family: var(--primary-ft);
          color: var(--d-green);
          margin-bottom: 6px;

          @include breakpoint(desktop) {
            font-size: 30px;
            margin-bottom: 8px;
          }
        }

        p {
          font-size: 22px;
          font-weight: weight(regular);
          font-family: var(--secondary-ft);
          color: var(--green);
          margin-bottom: 12px;

          @include breakpoint(desktop) {
            font-size: 24px;
            margin-bottom: 16px;
          }
        }

        button {
          height: 37px;
          width: 150px;
          border: 1px solid var(--green);
          border-radius: 30px;
          background: var(--green);
          text-align: center;
          font-family: var(--secondary-ft);
          font-size: 21px;
          font-weight: weight(semi-bold);
          color: var(--vl-green);
          cursor: pointer;
        }
      }
    }
  }
}
</style>
