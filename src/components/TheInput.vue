<template>
  <form @submit.prevent class="inputs-form">
    <div class="form-control flex flex-fd-c">
      <label for="bill">Bill</label>
      <input
        name="bill"
        type="text"
        placeholder="0"
        v-model="enteredBill"
        @blur="validateBillInput"
        :class="billValidity === 'invalid' ? 'error' : ''"
      />
      <img
        src="../assets/images/icon-dollar.svg"
        width="11"
        height="17"
        class="icon"
        alt="dollar icon"
      />
      <p class="error" v-if="billValidity === 'invalid'">Can't be zero</p>
    </div>

    <div class="tip">
      <div class="tip-label">Select Tip %</div>
      <div class="tip-controls flex flex-fw-w">
        <button
          :class="tipButtons['tip5'] ? 'active-btn' : ''"
          @click="getTipPercentage"
        >
          5%
        </button>
        <button
          :class="tipButtons['tip10'] ? 'active-btn' : ''"
          @click="getTipPercentage"
        >
          10%
        </button>
        <button
          :class="tipButtons['tip15'] ? 'active-btn' : ''"
          @click="getTipPercentage"
        >
          15%
        </button>
        <button
          :class="tipButtons['tip25'] ? 'active-btn' : ''"
          @click="getTipPercentage"
        >
          25%
        </button>
        <button
          :class="tipButtons['tip50'] ? 'active-btn' : ''"
          @click="getTipPercentage"
        >
          50%
        </button>
        <form class="tip-form">
          <label for="custom"></label>
          <input id="custom" name="custom" type="text" placeholder="Custom" />
        </form>
      </div>
    </div>

    <div class="form-control flex flex-fd-c">
      <label for="people">Number of People</label>
      <input
        name="people"
        type="text"
        placeholder="0"
        v-model="enteredPeople"
        @blur="validatePeopleInput"
        :class="peopleValidity === 'invalid' ? 'error' : ''"
      />
      <img
        src="../assets/images/icon-person.svg"
        width="13"
        height="16"
        class="icon"
        alt="person icon"
      />
      <p class="error" v-if="peopleValidity === 'invalid'">Can't be zero</p>
    </div>
  </form>
</template>


<script>
export default {
  data() {
    return {
      enteredBill: null,
      enteredPeople: null,
      billValidity: "pending",
      peopleValidity: "pending",
      tip: null,
      tipButtons: {
        tip5: null,
        tip10: null,
        tip15: null,
        tip25: null,
        tip50: null,
      },
    };
  },
  methods: {
    getTipPercentage(event) {
      const buttonText = event.target.innerText;
      this.tip = parseInt(buttonText.slice(0, -1));
      this.setBtnActiveStatus(this.tip);
    },
    setBtnActiveStatus(buttonValue) {
      this.resetActiveStatus();
      const buttonText = buttonValue + "%";
      switch (buttonText) {
        case "5%":
          this.tipButtons["tip5"] = buttonValue;
          break;
        case "10%":
          this.tipButtons["tip10"] = buttonValue;
          break;
        case "15%":
          this.tipButtons["tip15"] = buttonValue;
          break;
        case "25%":
          this.tipButtons["tip25"] = buttonValue;
          break;
        case "50%":
          this.tipButtons["tip50"] = buttonValue;
          break;
        default:
          break;
      }
    },
    resetActiveStatus() {
      for (const btn in this.tipButtons) {
        this.tipButtons[btn] = null;
      }
    },
    validateBillInput() {
      if (
        this.enteredBill === "" ||
        this.enteredBill === 0 ||
        this.enteredBill === null
      ) {
        this.billValidity = "invalid";
      } else {
        this.billValidity = "valid";
      }
    },
    validatePeopleInput() {
      if (
        this.enteredPeople === "" ||
        this.enteredPeople === 0 ||
        this.enteredPeople === null
      ) {
        this.peopleValidity = "invalid";
      } else {
        this.peopleValidity = "valid";
      }
    },
  },
};
</script>

<style scoped>
form.inputs-form {
  padding: 1.1875rem 1rem 0;
}

.form-control {
  position: relative;
}

.form-control:first-child,
.tip {
  margin-bottom: 2.875rem;
}

.form-control label,
.tip-label {
  color: var(--color-wintergreen-dream);
  font-size: var(--font-size-16);
  margin-bottom: 0.5rem;
}

.form-control input {
  width: 100%;
  padding: 0.375rem 1.0625rem 0.375rem 0;
  border-radius: 5px;
  border: none;
  font-family: inherit;
  font-weight: inherit;
  font-size: var(--font-size-24);
  text-align: right;
  color: var(--color-deep-jungle-green);
  background-color: var(--color-mint-cream);
}

.form-control input:focus {
  outline-color: var(--color-light-sea-green);
}

.form-control input:hover {
  outline: 2.5px solid var(--color-light-sea-green);
}

.form-control input::placeholder {
  color: var(--color-morning-blue);
}

.form-control img {
  position: absolute;
  top: 47px;
  left: 18px;
}

.tip-controls {
  gap: 0.85rem;
}

.tip-controls button,
.tip-controls .tip-form input {
  width: 7.3125rem;
  border-radius: 5px;
  border: none;
  font-family: inherit;
  font-weight: inherit;
  font-size: var(--font-size-24);
}

.tip-controls .tip-form input:focus {
  outline-color: var(--color-light-sea-green);
}

.tip-controls .tip-form input:hover {
  outline: 2.5px solid var(--color-light-sea-green);
}

.tip-controls button {
  padding: 0.375rem 0;
  cursor: pointer;
  color: var(--color-white);
  background-color: var(--color-deep-jungle-green);
  transition: all 0.2s ease-in-out;
}

.tip-controls button:hover {
  color: var(--color-deep-jungle-green);
  background-color: var(--color-crystal);
}

.tip-controls .tip-form input {
  padding: 6px 14px;
  text-align: right;
  color: var(--color-deep-jungle-green);
  background-color: var(--color-mint-cream);
}

.tip-controls .tip-form input::placeholder {
  color: var(--color-wintergreen-dream);
}

.tip-controls .active-btn {
  background-color: var(--color-light-sea-green);
  color: var(--color-deep-jungle-green);
}

p.error {
  position: absolute;
  right: 0;
  color: var(--color-red-pigment);
}

input.error {
  outline: 2.5px solid var(--color-red-pigment);
}

@media (max-width: 799px) {
  form.inputs-form {
    padding: 5px 8px 0;
  }

  .tip {
    margin-bottom: 2.375rem;
  }

  .tip-controls {
    gap: 1rem;
  }

  .tip-controls button,
  .tip-controls .tip-form input {
    width: 9.15625rem;
    max-width: 100%;
  }
}
</style>