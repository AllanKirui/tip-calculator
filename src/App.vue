<template>
  <section class="container">
    <header>
      <div>
        <img
          src="./assets/images/logo.svg"
          width="87"
          height="54"
          alt="tip calculator logo"
        />
      </div>
    </header>

    <div class="calculator-wrapper flex">
      <the-input
        @calculation-results="getCalculationResults"
        @reset-status="resetCalcStatus"
        :is-reset="isResetCalc"
      ></the-input>
      <the-output
        :tip-amount="tipPerPerson"
        :total-amount="totalPerPerson"
        @setStatus="setResetStatus"
      ></the-output>
    </div>

    <div class="attribution">
      Challenge by
      <a
        href="https://www.frontendmentor.io?ref=challenge"
        target="_blank"
        rel="noopener"
        >Frontend Mentor</a
      >. Coded by
      <a href="https://www.github.com/AllanKirui" target="_blank" rel="noopener"
        >Allan Kirui</a
      >.
    </div>
  </section>
</template>

<script>
import TheInput from "./components/TheInput.vue";
import TheOutput from "./components/TheOutput.vue";

export default {
  components: {
    "the-input": TheInput,
    "the-output": TheOutput,
  },
  data() {
    return {
      tipPerPerson: 0,
      totalPerPerson: 0,
      isResetCalc: false,
    };
  },
  methods: {
    getCalculationResults(tip, total) {
      this.tipPerPerson = tip;
      this.totalPerPerson = total;
    },
    setResetStatus() {
      this.isResetCalc = !this.isResetCalc;
    },
    resetCalcStatus() {
      this.tipPerPerson = 0;
      this.totalPerPerson = 0;
      this.isResetCalc = false;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Fjalla+One&family=Noto+Sans&family=Space+Mono:wght@400;700&display=swap");

:root {
  /* Colors */
  --color-light-sea-green: #26c0ac;
  --color-deep-jungle-green: #00494d;
  --color-wintergreen-dream: #5e7a7d;
  --color-morning-blue: #7f9d9f;
  --color-columbia-blue: #c5e4e7;
  --color-mint-cream: #f4fafa;
  --color-white: #ffffff;
  --color-crystal: #9fe8df;
  --color-water-blue: #0d686d;
  --color-red-pigment: #e52323;
  --color-deep-space-sparkle: #4a5f62;

  /* Font sizes */
  --font-size-13: 0.8125rem;
  --font-size-16: 1rem;
  --font-size-20: 1.25rem;
  --font-size-24: 1.5rem;
  --font-size-32: 2rem;
  --font-size-48: 3rem;

  /* Fonts */
  --font-space-mono: "Space Mono", sans-serif;
}

html {
  font-size: 100%;
  box-sizing: border-box;
}

*,
*::before,
*::after {
  box-sizing: inherit;
}

body {
  margin: 0;
  padding: 0;
  width: 100%;
  font-family: var(--font-space-mono);
  font-weight: 700;
  background-color: var(--color-columbia-blue);
}

p {
  margin: 0;
}

/* Flex box styles */
.flex {
  display: flex;
}

.flex-fd-c {
  flex-direction: column;
}

.flex-jc-c {
  justify-content: center;
}

.flex-jc-sb {
  justify-content: space-between;
}

.flex-ai-c {
  align-items: center;
}

.flex-fw-w {
  flex-wrap: wrap;
}
/* End of utility classes and resets */

.container {
  max-width: 57.5rem;
  margin: 0 auto;
}

header {
  margin-top: 10.125rem;
  margin-bottom: 5.40625rem;
  text-align: center;
}

.calculator-wrapper {
  width: 100%;
  gap: 2rem;
  padding: 2rem;
  border-radius: 20px;
  background-color: var(--color-white);
}

.attribution {
  text-align: center;
  margin-top: 2rem;
  margin-bottom: 2rem;
  padding: 0 2rem;
  line-height: 2;
  font-size: var(--font-size-16);
  color: var(--color-deep-space-sparkle);
}

.attribution a {
  position: relative;
  text-decoration: none;
  color: var(--color-deep-jungle-green);
}

.attribution a::before {
  content: "";
  position: absolute;
  left: 50%;
  transform: translateX(-50%);
  bottom: -9px;
  background-color: var(--color-deep-jungle-green);
  width: 0;
  height: 2px;
  transition: all 0.2s ease-in-out;
}

.attribution a:hover::before {
  width: 3.125rem;
}

@media (max-width: 1399px) {
  header {
    margin-top: 5.625rem;
    margin-bottom: 3.125rem;
  }
}

@media (max-width: 799px) {
  header {
    margin-top: 3rem;
    margin-bottom: 2.5rem;
  }

  .calculator-wrapper {
    flex-wrap: wrap;
    padding: 1.5rem;
    border-radius: 20px 20px 0 0;
  }
}
</style>