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

@import url(https://fonts.googleapis.com/css?family=Exo|Montserrat|Roboto);

#app {
  font-family: 'Roboto', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.btn-group {

  .btn,
  .btn-default {
    background: #f7be44;
    color: white;
    border: 2px solid #f7be44;
    font-weight: 900;
    font-family: 'Exo', sans-serif;
    transition: all ease 0.3s;

    &.active, &:focus {
      box-shadow: inset 0 0 5px rgba(255,255,255,0.5);
      border-color: blue;

      &:hover {
        color: white;
      }
    }
  }

  .btn:first-child {
    background: #671611;
    border: 2px solid #671611;
  }

  .btn:nth-child(2) {
    background: #ae2932;
    border: 2px solid #ae2932;
  }

  .btn:nth-child(3) {
    background: #ce3436;
    border: 2px solid #ce3436;
  }

  .btn:nth-child(8) {
    background: #8fc96f;
    border: 2px solid #8fc96f;
  }

  .btn:nth-child(9) {
    background: #5bb656;
    border: 2px solid #5bb656;
  }

  .btn:nth-child(10) {
    background: #21914c;
    border: 2px solid #21914c;
  }
}

.sv_main {
  background: none;
}

.panel-footer {
  background-color: none;
}
</style>
