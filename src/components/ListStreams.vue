<template>
  <div class="listStreams">
    <h3>{{ msg }}</h3>
    <br>
    <select v-model="selected" class="form-control" style="width: 30%" name="depart" id="depart">
      <option selected disabled>Choose</option>
      <option v-for="option in options" v-bind:value="option.value">{{ options.text }}</option>
    </select>
    <span>Selected: {{ selected }}</span>
  </div>
</template>

<script>
export default {
  name: "ListStreams",

  props: [],
  data() {
    return {
      selected: "Choose",
      options: [{ text: "a", value: "b" }]
    };
  },
  methods: {
    populate() {
      this.$http
        .get("https://postman-echo.com/get?foo1=bar1&foo2=bar2")
        .then(response => {
          console.log("response.data", response.data);
          response.body.args.forEach(obj => {
            this.option.push({ text: obj, value: obj });
          });
        });
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
