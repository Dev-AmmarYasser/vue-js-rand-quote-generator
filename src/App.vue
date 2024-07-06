<template>
  <div class="quote">
    <h2>{{ quotes[randNum].quote }}</h2>
    <h4>{{ quotes[randNum].author }}</h4>
  </div>
  <button @click="randomise">Generate Quote</button>
</template>

<script setup>
  import { ref } from "vue";

  import $quotes from "./quotes";

  const quotes = ref($quotes);

  const randNum = ref(0);

  function randomise() {
    randNum.value = Math.floor(Math.random() * (99 - 0) + 0);
  }

  // const neededQuote = quotes.value[randNum];

  // console.log(neededQuote.quote);
</script>

<style scoped>
  .quote {
    position: absolute;
    top: 40%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: fit-content;
    padding-right: 20px;
  }

  .quote h2 {
    text-align: center;
    font-weight: bold;
    font-size: 28px;
    font-family: "Noto Serif", serif;
  }

  .quote h2::before {
    content: "";
    background-image: url(/src/assets/quotes.png);
    position: absolute;
    width: 40px;
    height: 40px;
    display: block;
    background-size: contain;
    top: -11px;
    left: 100%;
  }

  .quote h4 {
    text-align: end;
    font-size: 20px;
    left: 30px;
    position: relative;
  }

  button {
    padding: 15px 35px;
    border-radius: 8px;
    border: none;
    background-color: #0ea5e9;
    color: #fff;
    font-weight: bold;
    font-size: 20px;
    cursor: pointer;
    user-select: none;
    transition: 300ms;
    position: absolute;
    top: 55%;
    left: 50%;
    transform: translate(-50%, -50%);
  }

  button:hover {
    background-color: #38bdf8;
  }
</style>
