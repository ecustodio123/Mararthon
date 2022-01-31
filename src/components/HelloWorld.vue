<template>
  <div class="hello">
    <h1>Marathon</h1>

    <div v-for=" (data, index) in dataMarathon" :key="index">

      <div class="bg-rectangle-dark">
        <img src="https://dummyimage.com/200x200/024983/ffffff&text=website" alt="" class="image-marathon">

        <h5 style="color: #ffffff">
        {{index}}. {{data.username}}
        </h5>
      </div>

      {{data}}

    </div>

    {{ dataMarathon }}
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      name: "HelloWorld",
      dataMarathon: [],
    };
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => (this.dataMarathon = response));
  },
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
.bg-rectangle-dark{
  background: #444444;
  height: 16rem;
  max-width: 12rem;
  border-radius: 0.40rem!important;
}
.image-marathon{
  height: 8rem;
  max-width: 10rem;
  border-radius: 0.40rem!important;
  margin: 20px;
}
</style>
