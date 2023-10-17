<template>
    <button
      :class="['base-button', `base-button-${color}`, { 'base-button-disabled': disabled }]"
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
      color: {
        type: String,
        default: 'primary',
        validator: (value) => {
          return ['primary', 'warn', 'danger'].includes(value);
        },
      },
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
    border: none;
    border-radius: 5px;
    cursor: pointer;
    transition: background-color 0.3s, transform 0.1s;
  }
  
  .base-button:hover {
    background-color: var(--button-hover-background, #0056b3);
    transform: scale(1.05);
  }
  
  .base-button:focus {
    outline: none;
    box-shadow: 0 0 3px 1px var(--button-focus-shadow, #0074d9);
  }
  
  .base-button-disabled {
    background-color: #ccc;
    cursor: not-allowed;
  }
  
  /* Color palette using CSS variables */
  .base-button-primary {
    background-color: var(--primary-color, #0074d9);
  }
  
  .base-button-warn {
    background-color: var(--warn-color, #ff9800);
  }
  
  .base-button-danger {
    background-color: var(--danger-color, #ff5733);
  }
  </style>
  