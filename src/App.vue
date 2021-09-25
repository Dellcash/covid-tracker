<template>
  <the-header />

  <div class="container ">
    <router-view />
  </div>
</template>

<script>
export default {
  components: {
    "the-header": require("@/components/TheHeader.vue").default,
  },
};
</script>

<style>
@font-face {
  font-family: "Vazir";
  src: url("./fonts/Vazir.eot");
  /* IE9 Compat Modes */
  src: url("./fonts/Vazir.eot?#iefix") format("embedded-opentype"),
    url("./fonts/Vazir.woff2") format("woff2"),
    url("./fonts/Vazir.woff") format("woff"),
    url("./fonts/Vazir.ttf") format("truetype");
  /* Safari, Android, iOS */
}

@font-face {
  font-family: "Mosa";
  src: url("./fonts/Mj_Mousa.TTF");
}
@font-face {
  font-family: "Parand";
  src: url("./fonts/Mj_Parand.TTF");
}
body {
  font-family: "Vazir" !important;
}
</style>
