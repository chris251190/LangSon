<template>
    <div id="app">
        <LangSon/>
        <TranslateForm v-on:formSubmit="translateText"></TranslateForm>
        <TranslateOutput v-text="translatedText"></TranslateOutput>
    </div>
</template>

<script>
    /* eslint-disable no-console */

    import LangSon from './components/LangSon.vue'
    import TranslateForm from './components/TranslateForm.vue'
    import TranslateOutput from './components/TranslateOutput.vue'

    export default {
        name: 'app',
        components: {
            LangSon,
            TranslateForm,
            TranslateOutput
        },
        data: function () {
            return {
                translatedText: ''
            }
        },
        methods: {
            translateText: function (text, language) {
                this.$http.get('https://translate.yandex.net/api/v1.5/tr.json/translate?key=trnsl.1.1.20170329T180255Z.3c18d2dc7b65d525.f23ed9a9efa992bded4ef96334e3c154f61d2dea&lang=' + language + '&text=' + text)
                    .then((response) => {
                        this.translatedText = response.body.text[0];
                    });
            }
        }
    }
</script>

<style>
    #app {
        font-family: 'Avenir', Helvetica, Arial, sans-serif;
        -webkit-font-smoothing: antialiased;
        -moz-osx-font-smoothing: grayscale;
        text-align: center;
        color: #2c3e50;
        margin-top: 60px;
    }
</style>
