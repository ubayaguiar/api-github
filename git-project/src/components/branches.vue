<template>
  <div>
    <ul class="branch">
      <li v-for="rama in branch" :key="rama.name">
        <input type="radio" name="commits" :value="rama.name" v-model="picked"> {{rama.name}}       
      </li>
    </ul>
    
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "branches",
  created () {
        axios
        .get(this.url)
        .then(res => this.branch = res.data)    
  },
  data() {
    return {
      msg: "Know your commits",
      branch: [],
      url: "https://api.github.com/repos/phobal/ivideo/branches?access_token=adfecbe383f1f0f96755d8d1b61c08dbf2ef7623",
      picked: ''
    };
  },
  methods: {
    
  }
};
</script>

<style scoped>
.branch {
  list-style-type: none;
  padding: 0;
}
.branch li{
  display: inline;
}
</style>

