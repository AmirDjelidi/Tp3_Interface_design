<template>
  <BaseButton
      :disabled="isPending"
      @click="handleClick"
  >
    <slot></slot>
  </BaseButton>
</template>

<script>
import BaseButton from './BaseButton.vue'; // Assurez-vous d'importer BaseButton

export default {
  components: {
    BaseButton
  },
  props: {
    color: {
      type: String,
      default: 'primary'
    }
  },
  data() {
    return {
      isPending: false // État pour suivre si une action est en cours
    };
  },
  methods: {
    // Méthode dédiée pour gérer le clic
    handleClick() {
      if (this.isPending) return; // Si déjà en attente, ne rien faire
      this.isPending = true; // Désactive le bouton

      // Simule une action asynchrone avec un délai de 2 secondes
      new Promise((resolve) => {
        setTimeout(() => {
          resolve();
        }, 2000); // Attente de 2 secondes
      }).finally(() => {
        this.isPending = false; // Réactive le bouton après 2 secondes
      });
    }
  }
};
</script>
