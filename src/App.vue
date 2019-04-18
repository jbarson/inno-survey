<template>
  <div id="app">
    <div id="surveyElement">
      <survey :survey='survey'/>
    </div>
    <div id="surveyResult">{{survey.data}}</div>
  </div>
</template>

<script>
  import * as SurveyVue from "survey-vue";
  import "bootstrap/dist/css/bootstrap.css";
  import * as widgets from "surveyjs-widgets";
  import ciobv from "../src/assets/CIOBV.json";
  import "./assets/styles/base.scss";
  import "./assets/styles/button-group.scss"

  const Survey = SurveyVue.Survey;
  Survey.cssType = "bootstrap";
  widgets.icheck(SurveyVue);
  widgets.select2(SurveyVue);
  widgets.inputmask(SurveyVue);
  widgets.jquerybarrating(SurveyVue);
  widgets.jqueryuidatepicker(SurveyVue);
  widgets.nouislider(SurveyVue);
  widgets.select2tagbox(SurveyVue);
  widgets.signaturepad(SurveyVue);
  widgets.sortablejs(SurveyVue);
  widgets.ckeditor(SurveyVue);
  widgets.autocomplete(SurveyVue);
  widgets.bootstrapslider(SurveyVue);
  export default {
    name: "app",
    components: {
      Survey
    },
    data() {
      const json = ciobv;
      const model = new SurveyVue.Model(json);
      return {
        survey: model
      };
    }
  };
</script>

<style lang='scss'>
  #app {
    font-family: 'Roboto', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
  }

  .sv_main {
    background: none;
  }

  .panel-footer {
    background-color: none;
  }
</style>
