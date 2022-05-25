<template>
  <footer>
    <div class="footer-section">
      <div class="footer-container">
        <div class="information">
          <div class="contact-info">
            <router-link to="/"><h4 class="logo">Greene</h4></router-link>
            <p class="address">
              Plot 2512b Adeyemo Akapo Street Omole Estate Phase 1,
              Lagos,Nigeria.
            </p>
            <div class="socials-links">
              <img src="@/assets/facebook-icon.svg" alt="facebook icon" />
              <img src="@/assets/instagram-icon.svg" alt="instagram icon" />
              <img src="@/assets/twitter-icon.svg" alt="twitter icon" />
            </div>
          </div>
          <div class="product-info">
            <router-link to="/#products"><h4>Products</h4></router-link>
            <router-link to="/indoor-plants"><p>Indoor Plants</p></router-link>
            <router-link to="/outdoor-plants"
              ><p>Outdoor Plants</p></router-link
            >
            <router-link to="/flower-seeds"><p>Flower Seeds</p></router-link>
            <router-link to="/garden-tools"><p>Garden Tools</p></router-link>
          </div>
          <div class="company-info">
            <h4>Information</h4>
            <router-link to="/about-us"><p>About Us</p></router-link>
            <router-link to="/join-our-team"><p>Join Our Team</p></router-link>
          </div>
        </div>
        <div class="copyright">
          <p>This website was designed and built by George</p>
        </div>
      </div>
    </div>
  </footer>
</template>

<script>
export default {};
</script>

<style lang="scss">
.footer-section {
  width: 100%;
  //   height: 450px;
  background: var(--d-green);

  .footer-container {
    width: min(90%, 1450px);
    margin: 0 auto;
    padding: 30px 0;
    @include flex(column, center);
    text-align: center;

    @include breakpoint(desktop) {
      text-align: left;
    }

    h4 {
      font-family: var(--primary-ft);
      font-size: 28px;
      color: var(--vl-green);
      font-weight: weight(bold);
      margin-bottom: 10px;
    }

    p {
      font-family: var(--secondary-ft);
      font-size: 20px;
      color: var(--vl-green);
      font-weight: weight(regular);
      margin-bottom: 7px;
    }

    .information {
      @include flex(column, center);

      @include breakpoint(desktop) {
        width: 100%;
        flex-direction: row;
        justify-content: flex-start;
        align-items: flex-start;
      }

      .contact-info,
      .product-info,
      .company-info {
        margin: 20px auto 0;

        @include breakpoint(desktop) {
          margin: 20px auto 0 0;
        }
      }

      .product-info,
      .company-info {
        h4 {
          font-size: 26px;
        }
      }

      .contact-info {
        p {
          margin-bottom: 12px;
          max-width: 450px;
        }
        .socials-links {
          width: 150px;
          margin: 0 auto;
          @include flex(row, space-between);

          @include breakpoint(desktop) {
            margin: 0;
          }
        }
      }
    }

    .copyright {
      p {
        font-weight: weight(semi-bold);
        margin-top: 32px;
        text-align: center;
      }
    }
  }
}
</style>