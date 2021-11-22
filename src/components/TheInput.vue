<template>
  <form>
    <div class="form-control">
      <label for="bill">Bill</label>
      <input id="bill" name="bill" type="text" />
      <img
        src="../assets/images/icon-dollar.svg"
        class="icon"
        alt="dollar icon"
      />
    </div>

    <div class="tip">
      <div class="tip-title">Select Tip %</div>
      <div class="tip-control">
        <button>5%</button>
        <button>10%</button>
        <button>15%</button>
        <button>25%</button>
        <button>50%</button>
        <form class="tip-form">
          <label for="custom"></label>
          <input id="custom" name="custom" type="text" />
        </form>
      </div>
    </div>

    <div class="form-control">
      <label for="people">Number of People</label>
      <input id="people" name="people" type="text" />
      <img
        src="../assets/images/icon-person.svg"
        class="icon"
        alt="person icon"
      />
    </div>
  </form>
</template>