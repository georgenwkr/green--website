<template>
  <div class="newsletter-section">
    <div class="newsletter-container">
      <h2>Sign up to our newsletter</h2>
      <p>
        Get exclusive promotions, new products and more. We promise to not spam
        you.
      </p>
      <form action="#">
        <input type="text" placeholder="enter email..." required />
        <button>Subscribe</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {};
</script>

<style lang="scss">
.newsletter-section {
  width: 100%;

  .newsletter-container {
    width: 90%;
    margin: 120px auto;
    text-align: center;

    h2 {
      font-family: var(--primary-ft);
      font-weight: weight(bold);
      font-size: 30px;
      color: var(--d-green);

      @include breakpoint(desktop) {
        font-size: 42px;
      }
    }

    p {
      font-family: var(--secondary-ft);
      font-weight: weight(regular);
      font-size: 20px;
      color: var(--green);
      margin: 20px auto;
      width: 330px;

      @include breakpoint(desktop) {
        font-size: 25px;
        width: 100%;
      }
    }

    form {
      @include flex(column, center);

      @include breakpoint(desktop) {
        flex-direction: row;
      }

      input {
        width: min(90%, 380px);
        height: 57px;
        border: none;
        border-radius: 30px;
        background: var(--l-green);
        color: var(--green);
        outline: none;
        font-family: var(--secondary-ft);
        font-weight: weight(regular);
        font-size: 20px;
        padding: 0 20px;
        margin: 8px 0;

        &::placeholder {
          font-family: var(--secondary-ft);
          font-weight: weight(regular);
          font-size: 20px;
          color: var(--green);
        }
      }

      button {
        height: 58px;
        width: 182px;
        border: none;
        border-radius: 30px;
        background: var(--green);
        color: var(--vl-green);
        font-size: 25px;
        font-family: var(--secondary-ft);
        font-weight: weight(semi-bold);
        margin: 8px 4px;
        cursor: pointer;
      }
    }
  }
}
</style>