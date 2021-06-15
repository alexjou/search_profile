<template>
  <div class="home">
    <Navbar/>
    <div class="mx-4 flex flex-col">
      <div class="p-4 text-center flex flex-col items-center">
        <h1 class="text-2xl">Pesquise usuários do Github</h1>
        <p class="my-2">Digite um nome para encontrar usuários ou repositórios</p>
        <input
          @keyup="getUser"
          id="search"
          type="text"
          class="form-control w-1/4"
          required
        />
      </div>
      <div class="flex flex-row mt-3" v-if="user.length !== 0">
        <div class="col-md-4">
          <Profile :user="user" />
        </div>
        <div class="col-md-8">
          <Repo v-for="repo in repos" :key="repo" :repo="repo" />
        </div>
      </div>
    </div>
  </div>
</template>


<script>
import Navbar from "../components/Navbar.vue";
import Profile from "../components/Profile.vue";
import Repo from "../components/Repo.vue";
import axios from "axios";

export default {
  name: "Home",
  data() {
    return {
      github: {
        url: "https://api.github.com/users",
        client_id: "79b50ba992f502c97385",
        client_secret: "3febeb7d2c5a464a56547a6d5d5c5e21024178ff",
        count: 7,
        sort: "created: asc",
      },
      user: [],
      repos: [],
    };
  },
  components: {
    Navbar,
    Profile,
    Repo,
  },
  methods: {
    getUser(doc) {
      const user = doc.target.value;
      const { url, client_id, client_secret, count, sort } = this.github;

      axios
        .get(
          `${url}/${user}?client_id=${client_id}&client_secret=${client_secret}`
        )
        .then(({ data }) => (this.user = data));

      axios
        .get(
          `${url}/${user}/repos?per_page=${count}&sort${sort}&client_id=${client_id}&client_secret=${client_secret}`
        )
        .then(({ data }) => (this.repos = data));
    },
  },
};
</script>

