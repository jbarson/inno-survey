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
import $ from "jquery";
import "./assets/styles/base.scss";
import "./assets/styles/typography.scss";
import "./assets/styles/buttons.scss"
import "./assets/styles/checkboxes.scss"
import "./assets/styles/textarea.scss"
import "./assets/styles/text-input.scss"
import "./assets/styles/button-group.scss"
import "./assets/styles/footer.scss"
import "./assets/styles/progress-bar.scss"
import "./assets/styles/alerts.scss"
import "./assets/styles/header.scss"
import "./assets/styles/question.scss"
import "./assets/styles/ranking.scss"

  const Survey = SurveyVue.Survey;

  // Survey
  //   .onComplete
  //   .add(function (result) {
  //       document
  //           .querySelector('#surveyResult')
  //           .innerHTML = "result: " + JSON.stringify(result.data);
  //   });

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
