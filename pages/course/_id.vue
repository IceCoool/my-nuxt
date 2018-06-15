<template>
    <div>
    sss
    </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  asyncData({ params, query}) {
    return {
      id: params.id,
      type: query.type,
    };
  }
};
</script>

<style lang="scss">
</style>