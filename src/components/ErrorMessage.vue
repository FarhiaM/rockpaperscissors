<!-- /src/components/ErrorMessage.vue -->
<template>
  <div class="errorMessage">
    <p>{{ this.$store.state.error }}</p>
  </div>
</template>

<script>
export default {
  name: 'ErrorMessage',
  methods: {
    dismiss() {
      this.$store.state.error = '';
    },
  },
};
</script>

<style style="scss" scoped>

p{
  color:red;
  padding: 10px 30px;
}
</style>
