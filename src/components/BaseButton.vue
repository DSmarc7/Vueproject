<template>
    <button
      :class="['base-button', { 'base-button-disabled': disabled }]"
      :style="{ margin: margin }"
      @click="handleClick"
      @mouseenter="isHovered = true"
      @mouseleave="isHovered = false"
      @focus="isFocused = true"
      @blur="isFocused = false"
      :disabled="disabled" 
    >
      <slot></slot>
    </button>
  </template>
  
  <script>
  export default {
    data() {
      return {
        isHovered: false,
        isFocused: false,
      };
    },
    props: {
      disabled: Boolean,
      margin: String,
    },
    methods: {
      handleClick() {
        if (!this.disabled) {
          this.$emit('click');
        }
      },
    },
  };
  </script>
  
  <style scoped>
  .base-button {
    padding: 10px 20px;
    background-color: #0074d9; /* Primary color for the button */
    color: #fff;
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.1s;
  }
  
  .base-button:hover {
    background-color: #0056b3; /* Darker color on hover */
    transform: scale(1.05);
  }
  
  .base-button:focus {
    outline: none;
    box-shadow: 0 0 3px 1px #0074d9; /* Add a box shadow on focus */
  }
  
  .base-button-disabled {
    background-color: #ccc; /* Grayed out color for the disabled state */
    cursor: not-allowed;
  }
  </style>
  