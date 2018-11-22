<template>
  <div>
    <div class="train-controls">
      <h2 class="section col-sm-1">Training Data (x,y) pairs</h2>
      <div class="field-label">X</div><div class="field-label">Y</div>

      <div v-for="(item, index) in xValues" v-bind:key="index">
        <div>

          <div class="col-sm-1">
            <input class="field field-x" v-model="xValues[index]" type="number">
            <input class="field field-y" v-model="yValues[index]" type="number">
          </div>
        </div>
      </div>

      <button class="button-add-example button--green" v-on:click="addItem">+</button>
      <button class="button-train button--green" v-on:click="train">Train</button>
    </div>

    <div class="predict-controls">
      <h2 class="section col-sm-1">predicting</h2>
      <input class="field element" v-model="valueToPredict" type="number" placeholder="Enter an integer number"><br>
      <div class="element">{{ predictedValue }}</div>
      <button class="element button--green" v-on:clicl="predict" :disabled="!trained">predict</button>
    </div>

  </div>
</template>

<script>
export default {
  data () {
    return {
      trained: false,
      xValues: [1,2,3,4],
      yValues: [1,3,5,7],
      predictedValue: 'Click on train!',
      valueToPredict: '',
    }
  },
  methods: {
    addItem () {
      console.log("add!")
      this.xValues.push(0);
      this.yValues.push(0);
    },
    train () {
    },
    predict () {

    },
  }
}
</script>

<style>
.field, .field-label {
  height: 30px;
  float: left;
  padding: 0px, 15px;
  float: left;
  width: 50%;
}

.field {
  border-radius: 0px 5px 5px 0px;
  border: 1px solid #eee;
  margin-bottom: 15px;
  height: 40px;
}

.col-sm-1:after {
  content: "";
  display: table;
  clear: both;
}

.section, .field-label {
  text-align: left;
  font-family: "Quicksand", "Source Sans Pro" -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, "Helvetica Neue", "Arial", sans-serif;
  font-weight: 100;
}

.field-label {
  font-weight: 700;
}

.button-add-example {
  width: 100%;
  margin-bottom: 10px;
}

.button-train {
  width: 100%;
}

.predict-controls {
  padding-top: 30px;
  padding-bottom: 30px;
}

.predict-controls .element {
  width: 50%;
  display: block;
}

button {
  margin-top: 10px;
  font-family: "Quicksand", "Source Sans Pro" -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, "Helvetica Neue", "Arial", sans-serif;
  font-weight: 700;
}

</style>

