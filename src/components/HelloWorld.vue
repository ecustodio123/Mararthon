<template>
  <div class="hello" style="padding: 20px">
    <h1>Marathon</h1>
    <div class="test" style="overflow-x: auto">
      <div v-for="(data, index) in dataMarathon" :key="index">
        <div class="bg-rectangle-dark">
          <img
            src="https://dummyimage.com/200x200/024983/ffffff&text=website"
            alt=""
            class="image-marathon"
          />

          <h5 class="h5-marathon" style="text-align: center">
            {{ index }}. {{ data.username }}
          </h5>
          <div class="mx-5">
            <div class="d-flex" style="justify-content: space-evenly;">
              <h6 class="subtitle">Name:</h6>
              <h6 class="description">{{ data.name }}</h6>
            </div>
            <div class="d-flex" style="justify-content: space-evenly;">
              <h6 class="subtitle">Email:</h6>
              <h6 class="description">{{ data.email }}</h6>
            </div>
            <div class="d-flex" style="justify-content: space-evenly;">
              <h6 class="subtitle">Company:</h6>
              <h6 class="description">{{ data.company.name }}</h6>
            </div>
            <div class="d-flex" style="justify-content: space-evenly;">
              <h6 class="subtitle">City:</h6>
              <h6 class="description">{{ data.address.city }}</h6>
            </div>
          </div>
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
  margin: 20px 10px;
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
.subtitle{
  color: #6e6e6e;
}
.description{
  color: #FFFFFF;
}
</style>
