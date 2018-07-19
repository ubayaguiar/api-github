<template>
  <div>
    <ul>
      <li v-for="commit in commits" :key="commit.sha">
        {{commit.commit.message}}
      </li>
    </ul>
  </div>
</template>

<script>
import axios from "axios";
export default {
  name: "commit",
  created () {
    this.getCommits();
  },
  data() {
    return {
      url: "https://api.github.com/repos/phobal/ivideo/commits?sha="+this.branch+"&access_token=adfecbe383f1f0f96755d8d1b61c08dbf2ef7623",
      commits: []
     
    };
  },
  props: ['branch'],
  methods: {
    getCommits() {
      axios
        .get(this.url)
        .then(res => this.commits = res.data)
        .catch(console.log("ahora tampoco"));
    }
    
  }
};
</script>
