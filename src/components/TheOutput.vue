<template>
  <div class="output-wrapper">
    <div class="output-control flex flex-ai-c flex-jc-sb">
      <div class="label-wrapper flex flex-fd-c">
        <p class="label">Tip Amount</p>
        <p class="sub-label">/ person</p>
      </div>
      <div class="results-wrapper">
        <p class="results">${{ tipAmount === 0 ? "0.00" : tipAmount }}</p>
      </div>
    </div>

    <div class="output-control flex flex-ai-c flex-jc-sb">
      <div class="label-wrapper flex flex-fd-c">
        <p class="label">Total</p>
        <p class="sub-label">/ person</p>
      </div>
      <div class="results-wrapper">
        <p class="results">${{ totalAmount === 0 ? "0.00" : totalAmount }}</p>
      </div>
    </div>

    <div class="button-wrapper">
      <button
        :class="totalAmount === 0 ? 'disabled' : ''"
        @click="$emit('set-status')"
      >
        Reset
      </button>
    </div>
  </div>
</template>

<script>
export default {
  props: ["tipAmount", "totalAmount"],
  emits: ["set-status"],
};
</script>

<style scoped>
.output-wrapper {
  padding: 3.25rem 2rem 2.4375rem;
  border-radius: 15px;
  background-color: var(--color-deep-jungle-green);
  max-width: 25.8125rem; /* 413px */
  width: 100%;
}

.output-control p {
  margin: 0;
  padding: 0;
}

.output-control:first-child {
  margin-bottom: 1.375rem;
}

.label-wrapper .label {
  font-size: var(--font-size-16);
  color: var(--color-white);
}

.label-wrapper .sub-label {
  font-size: var(--font-size-13);
  color: var(--color-morning-blue);
}

.results {
  font-size: var(--font-size-48);
  color: var(--color-light-sea-green);
}

.button-wrapper {
  margin-top: 7.8125rem;
}

.button-wrapper button {
  width: 100%;
  height: 3rem;
  border-radius: 5px;
  border: none;
  font-family: inherit;
  font-weight: inherit;
  font-size: var(--font-size-20);
  background-color: var(--color-light-sea-green);
  color: var(--color-deep-jungle-green);
  text-transform: uppercase;
  cursor: pointer;
  transition: all 0.2s ease-in-out;
}

.button-wrapper button:hover {
  background-color: var(--color-crystal);
}

.button-wrapper button.disabled {
  background-color: var(--color-water-blue);
  pointer-events: none;
}

@media (max-width: 799px) {
  .output-wrapper {
    max-width: 100%;
    padding-top: 2.25rem;
  }

  .output-control:first-child {
    margin-bottom: 1.75rem;
  }

  .results {
    font-size: var(--font-size-32);
  }

  .button-wrapper {
    margin-top: 2.25rem;
  }
}
</style>