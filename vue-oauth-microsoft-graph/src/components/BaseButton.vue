<template>
  <button
      :disabled="isDisabled"
      :style="buttonStyles"
      @click="handleClick"
      @mouseover="isHovered = true"
      @mouseleave="isHovered = false"
  >
    <slot></slot>
  </button>
</template>

<script>
const colorPalette = {
  primary: { bg: '#42b983', hoverBg: '#4cce93', focusBorder: '#47d696' },
  warn: { bg: '#ff5722', hoverBg: '#ff7043', focusBorder: '#ff8a65' },
  danger: { bg: '#e53935', hoverBg: '#ef5350', focusBorder: '#e57373' }
};

export default {
  props: {
    color: {
      type: String,
      default: 'primary',
      validator(value) {
        return ['primary', 'warn', 'danger'].includes(value);
      }
    },
    disableOnClick: { // Nouvelle prop pour déterminer si le bouton doit être désactivé après un clic
      type: Boolean,
      default: false // Par défaut, les boutons ne sont pas désactivables
    }
  },
  data() {
    return {
      isDisabled: false,
      isHovered: false
    };
  },
  computed: {
    buttonStyles() {
      const palette = colorPalette[this.color];
      return {
        backgroundColor: this.isHovered ? palette.hoverBg : palette.bg,
        color: 'white',
        border: `2px solid ${palette.focusBorder}`,
        borderRadius: '25px',
        width: '150px',
        height: '50px',
        cursor: this.isDisabled ? 'not-allowed' : 'pointer',
        opacity: this.isDisabled ? 0.6 : 1,
        transition: 'all 0.3s ease'
      };
    }
  },
  methods: {
    handleClick() {
      // Désactive le bouton seulement si 'disableOnClick' est vrai
      if (this.disableOnClick && !this.isDisabled) {
        this.isDisabled = true;
      }
    }
  }
};
</script>

<style scoped>
button {
  border-radius: 25px;
  width: 120px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  border: 2px solid transparent;
  transition: transform 0.3s, background-color 0.3s;
}

button:hover {
  transform: scale(1.05);
}

button:disabled {
  cursor: not-allowed;
  opacity: 0.6;
}
</style>
