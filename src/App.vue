<template>
  <div id="app">  
    <div id="surveyElement">
      <img src="./assets/images/itrg-logo.svg" id="logo">
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
import "./assets/styles/typography.scss";
import "./assets/styles/buttons.scss"
import "./assets/styles/textarea.scss"
import "./assets/styles/text-input.scss"
import "./assets/styles/button-group.scss"
import "./assets/styles/footer.scss"
import "./assets/styles/progress-bar.scss"
import "./assets/styles/alerts.scss"
import "./assets/styles/header.scss"
import "./assets/styles/question.scss"

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
    font-family: "Roboto", Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    background-color:#fff;
    background-image:linear-gradient(135deg, transparent 0%, #fff 25%, #fff 75%, transparent 100%), url(data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAgAAAAICAYAAADED76LAAAAIklEQVQoU2N89+7dfwYsQEhIiBEkzDgkFGDzAbIY2Cv4AACvrBgJjYNGfwAAAABJRU5ErkJggg==);
  
  }
</style>