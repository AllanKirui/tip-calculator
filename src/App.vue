<template>
  <header></header>
</template>

<style>
:root {
  /* Colors */
  --color-light-sea-green: #26c0ac;
  --color-deep-jungle-green: #00494d;
  --color-wintergreen-dream: #5e7a7d;
  --color-morning-blue: #7f9d9f;
  --color-columbia-blue: #c5e4e7;
  --color-mint-cream: #f4fafa;
  --color-white: #ffffff;

  /* Font sizes */
  --font-size-13: 13px;
  --font-size-16: 16px;
  --font-size-20: 20px;
  --font-size-24: 24px;
  --font-size-32: 32px;
  --font-size-48: 48px;

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
</style>