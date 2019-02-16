<template>
      <form id="transForm" v-on:submit="formSubmit">
        <input type="text" v-model="textToTranslate" placeholder="Enter a Word...">
        <select v-model="language">
          <option value="ru">Russian</option>
          <option value="es">Spanish</option>
          <option value="fr">French</option>
          <option value="zh">Chinese</option>
          <option value="de">German</option>
          <option value="jp">Japanese</option>
        </select>
        <input type="submit" value="Translate">
      </form>
</template>

<script>
export default {
  name: 'translateForm',
  data(){
    return {
      textToTranslate:'',
      language:''
    }
  },
  created() {
    this.language = 'ru';
  },
  methods: {
    formSubmit(e){
      this.$emit('formSubmit', this.textToTranslate, this.language);
      e.preventDefault();
    }
  }
}
</script>

<style>
  #transForm{
    border-radius:10px;
    border: 1px #ccc solid;
  }
</style>
