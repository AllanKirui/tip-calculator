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
      <the-input></the-input>
      <the-output></the-output>
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