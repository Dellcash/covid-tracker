<template>
  <div class="grid md:grid-cols-2 gap-4">
    <!-- Box 1 -->
    <div class="shadow-md bg-blue-100 p-10 text-center rounded">
      <h3 class="text-4xl text-blue-900 font-bold mb-4 mosa">موارد جدید</h3>

      <div class="parand text-2xl mb-4">
        <span class="font-bold">جدید:</span>
        {{ numberWithCommas(stats.NewConfirmed) }}
      </div>
      <div class="parand text-2xl mb-4">
        <span class="font-bold">جمع:</span>
        {{ numberWithCommas(stats.TotalConfirmed) }}
      </div>
    </div>

    <!-- Box 2 -->
    <div class="shadow-md bg-blue-200 p-10 text-center rounded">
      <h3 class="text-4xl text-blue-900 font-bold mb-4 mosa">مرگ و میر</h3>

      <div class="parand text-2xl mb-4">
        <span class="font-bold">جدید:</span>
        {{ numberWithCommas(stats.NewDeaths) }}
      </div>
      <div class="parand text-2xl mb-4">
        <span class="font-bold">جمع:</span>
        {{ numberWithCommas(stats.TotalDeaths) }}
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['stats'],
  setup () {
    return {
      numberWithCommas (x) {
        return x.toString()
          .replace(/\B(?=(\d{3})+(?!\d))/g, '،');
      }
    };
  }
};
</script>

<style scoped>
.parand{
  font-family: "Parand";
}
.mosa{
  font-family: 'Mosa'
}
</style>