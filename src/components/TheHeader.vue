<template>
  <header>
    <button v-if="step === 1" @click="handleGoToHome">
      <i class="fab fa-vuejs"></i> Home
    </button>
    <button v-if="step === 2 || step === 3" @click="handleGoToHome">
      <i class="fas fa-arrow-left"></i>Cancel
    </button>
    <button v-if="step === 2" @click="handleNextStep">
      Next
      <i class="fas fa-arrow-right"></i>
    </button>
    <button v-if="step === 3" @click="handleSharePost">
      <i class="fa fa-share"></i>Share
    </button>
  </header>
</template>

<script>
export default {
  name: "TheHeader",
  props: {
    step: {
      type: Number,
      default: 1
    }
  },

  methods: {
    handleGoToHome() {
      this.$emit("go-to-home");
    },
    handleNextStep() {
      this.$emit("next-step");
    },
    handleSharePost() {
      this.$emit("share-post");
    }
  }
};
</script>

<style lang="scss" scoped>
header {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  height: 50px;
  background-color: #041e30;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 0 20px;
  z-index: 10;

  button {
    color: #816565;
    font-weight: bold;
    cursor: pointer;
  }
}
</style>