<template>
  <label :for="value">
    <input type="radio" class="radio" :name="name" :id="value" :value="value">
    <span>{{ value }}</span>
  </label>
</template>

<script>
export default {
  name: 'RadioButton',
  props: {
    name: {
      type: String,
      required: true,
    },
    value: {
      type: [String, Number],
      required: true,
    },
  },
};
</script>

<style lang="scss" scoped>

input[type="radio"] {
  display: none;
  }

span {
  padding: 10px 20px;
  white-space:nowrap;
  border: 1px solid #3F36CE;
  font-size: 18px;
  border-radius: 4px;
}
input[type="radio"]:checked ~ span {
  background: #78E6FC;
}


</style>
