<template>
  <div class="hello">
    <h1>Marathon</h1>
    <div class="test">
      <div v-for="(data, index) in dataMarathon" :key="index">
        <div class="bg-rectangle-dark">
          <img
            src="https://dummyimage.com/200x200/024983/ffffff&text=website"
            alt=""
            class="image-marathon"
          />

          <h5 class="h5-marathon">{{ index }}. {{ data.username }}</h5>
        </div>

        <br /><br />
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";
export default {
  data() {
    return {
      name: "HelloWorld",
      dataMarathon: {},
    };
  },
  created() {
    axios
      .get("https://jsonplaceholder.typicode.com/users")
      .then((response) => (this.dataMarathon = response.data));
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
.bg-rectangle-dark {
  background: #444444;
  height: 350px;
  width: 200px;
  border-radius: 0.4rem !important;
  margin-right: 20px;
}
.image-marathon {
  height: auto;
  width: 180px;
  border-radius: 0.4rem !important;
  margin: 20px 0px;
}
.test {
  display: flex !important;
}
.h5-marathon {
  color: #ffffff;
  margin-top: 0px;
  margin-bottom: 0px;
  font-size: 18px;
}
</style>
