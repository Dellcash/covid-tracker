<template>
  <div class="text-center">
    <h2 class="text-3xl font-bold">{{ text }}</h2>
    <div class="text-2xl mt-4 mb10 parand">{{ timestamp }}</div>
  </div>
</template>

<script>
import moment from 'jalali-moment'

export default {
  props: ["text", "dataDate"],
  computed: {
    timestamp: function() {
      return moment(this.dataDate).format('jYYYY/jMM/jDD, h:mm:ss');
    },
  },
};
</script>

<style scoped>
.parand{
  font-family: 'Parand';
}
</style>
