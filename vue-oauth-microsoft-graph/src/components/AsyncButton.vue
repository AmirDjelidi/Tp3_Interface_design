<template>
  <BaseButton
      :isDisabled="isPending"
  :color="color"
  @click="handleClick"
  >
  <!-- Affiche le texte de chargement pendant que le bouton est désactivé -->
  <span v-if="isPending">Loading...</span>
  <slot v-else></slot>
  </BaseButton>
</template>

<script>
import BaseButton from './BaseButton.vue';

export default {
  name: 'AsyncButton',
  components: { BaseButton },
  inheritAttrs: false,  // Empêche la transmission automatique des attributs natifs
  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },
  data() {
    return {
      isPending: false  // État pour savoir si le bouton est en cours de chargement
    };
  },
  methods: {
    handleClick() {
      if (!this.isPending) {  // Empêche plusieurs clics pendant l'état "pending"
        this.isPending = true;  // Désactive le bouton

        // Simule une action asynchrone (délai de 2 secondes)
        setTimeout(() => {
          this.isPending = false;  // Réactive le bouton après 2 secondes
        }, 2000);
      }
    }
  }
};
</script>
