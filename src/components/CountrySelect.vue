<template>
  <select @change="onChange()" v-model="selected" class="form-select block w-full border p-3 rounded mt-10">
    <option class="mosa"  value="0" >انتخاب کشور</option>
    <option style="direction: ltr;"  v-for="country in countries"  :value="country.ID">{{ country.Country }}</option>
  </select>
</template>

<script>
  export default {
    props:['countries'],
    data(){
      return{
        selected: 0
      }
    },
    methods:{
      onChange(){
        const country = this.countries.find(item => item.ID === this.selected)
        this.$emit('get-country', country)
      }
    }
  }
</script>

<style scoped>
option{

  font-family:'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif
}
.mosa{
  font-family:'Mosa'
}
</style>