<template>
    <form
      action="#"
      @submit="handleCalculate"
      class="flex flex-col items-center justify-center gap-4 p-10 border-2 rounded-lg border-violet-950"
    >
      <label for="a" class="text-xl font-light text-violet-50">Enter number A:</label>
      <input
        id="a"
        v-model.number="a"
        type="number"
        placeholder="Number A"
        class="text-center text-black rounded-lg outline-violet-950"
      />
      <label for="b" class="text-xl font-light text-violet-50">Enter number B:</label>
      <input
        id="b"
        v-model.number="b"
        type="number"
        placeholder="Number B"
        class="text-center text-black rounded-lg outline-violet-950"
      />
      <label for="operator" class="text-xl font-light text-violet-50">Select an operator:</label>
      <select id="operator" v-model="operator" class="text-center text-black rounded-lg outline-violet-950">
        <option value="+">+</option>
        <option value="-">-</option>
        <option value="*">*</option>
        <option value="/">/</option>
        <option value="%">%</option>
      </select>
      <button
        type="submit"
        class="p-2 font-semibold rounded-lg bg-gradient-to-r from-violet-800 to-violet-950 text-violet-50"
      >
        Calculate
      </button>
      <p class="text-xl font-light text-center w-fit text-violet-50">{{ result }}</p>
    </form>
  </template>
