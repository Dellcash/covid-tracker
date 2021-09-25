<template>
  <main v-if="!loading">
    <data-title :text="title" :dataDate="dataDate" />
    <data-boxes :stats="stats" />
    <country-select @get-country="getCountryData" :countries="countries" />

    <button
      v-if="stats.Country"
      @click="clearCountryData"
      class="bg-green-700 text-white rounded p-2 my-10 focus:outline-none hover:bg-green-600"
    >
      ریست
    </button>
  </main>

  <main class="mt-48 text-center" v-else>
    <img :src="loadingImage" class="w-24 m-auto" alt="" />
  </main>
</template>

<script>
export default {
  components: {
    "data-title": require("@/components/DataTitle.vue").default,
    "data-boxes": require("@/components/DataBoxes.vue").default,
    "country-select": require("@/components/CountrySelect.vue").default,
  },
  data() {
    return {
      loading: true,
      title: "جهانی",
      dataDate: "",
      stats: {},
      countries: [],
      loadingImage: require("@/assets/hourglass.gif"),
    };
  },
  methods: {
    async fetchCovidData() {
      const res = await fetch("https://api.covid19api.com/summary");
      const data = await res.json();
      return data;
    },
    getCountryData(country) {
      this.stats = country;
      this.title = country.Country;
    },
    async clearCountryData() {
      this.loading = true;
      const data = await this.fetchCovidData();
      this.title = "جهانی";
      this.stats = data.Global;
      this.loading = false;
    },
  },
  async created() {
    const data = await this.fetchCovidData();
    this.dataDate = data.Date;
    this.stats = data.Global;
    this.countries = data.Countries;
    this.loading = false;
  },
};
</script>
