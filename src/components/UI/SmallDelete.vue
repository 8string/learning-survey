<template>
  <button>
    <slot></slot>
  </button>
</template>


<style scoped>
button {
  font: inherit;
  border: 1px solid black;
  background-color: rgb(10, 46, 8);
  color: white;
  cursor: pointer;
}

button:hover,
button:active {
  background-color: #5c0556;
  border-color: #5c0556;
}
</style>