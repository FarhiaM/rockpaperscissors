<template>
  <div class="results">
    <div v-if="result" class="winner">
      <p>
        You won! 🎉
      </p>
      <iframe
        src="https://giphy.com/embed/Qadbv0ccmSrJL9Vlwj"
        frameBorder="0"
        class="giphy-embed"
        allowFullScreen
      ></iframe>
    </div>
    <div v-else class="looser">
      <p>
        You Lost! 😔
      </p>
      <iframe
        src="https://giphy.com/embed/dXXPEOlvsiOFozOlLu"
        frameBorder="0"
        class="giphy-embed"
        allowFullScreen
      ></iframe>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Result',
  props: {
    result: {
      type: Boolean,
      default: false,
    },
  },
};
</script>

<style lang="scss" scoped>
p {
  font-size: 1em;
}
iframe {
  margin-bottom: 100px;
}
</style>
