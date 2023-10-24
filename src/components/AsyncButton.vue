<template>
  <base-button
    :disabled="isPending"
    :color="color"
    @click.stop.prevent="handleClick"
  >
    <font-awesome-icon
      v-if="isPending"
      :icon="['fas', 'circle-notch']"
      pulse
    />
    <slot />
  </base-button>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  name: 'AsyncButton',
  components: { BaseButton },
  inheritAttrs: false,

  props: {
    color: {
      type: String,
      default: 'primary',
    },
  },

  data() {
    return {
      isPending: false,
    };
  },

  methods: {
    async handleClick() {
      // Trigger the loading state when the button is clicked
      this.isPending = true;
      try {
        // Emit a custom event to indicate that the action has started
        this.$emit('action-started');
        // Call the original click handler (using this.$attrs.onClick)
        const originalOnClick = this.$attrs.onClick;
        if (typeof originalOnClick === 'function') {
          await originalOnClick();
        }
      } finally {
        // Ensure loading state is reset after the action is completed
        this.isPending = false;
        // Emit a custom event to indicate that the action has completed
        this.$emit('action-completed');
      }
    },
  },
};
</script>
