<template>
    <button class="button" :type="type">{{ text }}</button>
</template>

<script>
export default {
  name: 'TheButton',
  props: {
    type: String,
    text: String,
  },
};
</script>

<style scoped lang="scss">
button{
  background: #78E6FC;
  padding: 10px 20px;
  border: 1px solid #78E6FC;
  font-size:1.5em;
  border-radius: 4px;
  outline:none;
}

button:hover, button:focus{
  transform: translateY(-3px);
}
</style>
