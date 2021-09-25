<template> 
  <div class="text-center parand">
    <h2 class="text-5xl Vazir">{{ text }}</h2>
    <div class="text-2xl mt-4 mb-10 parand">{{ timestamp }}</div>
  </div>
</template>

<script>
import moment from 'jalali-moment'

export default {
  props: ["text", "dataDate"],
  computed: {
    timestamp: function() {
      return moment(this.dataDate).format('jYYYY/jMM/jDD، h:mm:ss');
    },
  },
};
</script>

<style scoped>
.parand{
  font-family: 'Parand';
}
</style>
