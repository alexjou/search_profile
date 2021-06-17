<template>
  <div class="about">
    <Navbar />
    <div class="flex items-center justify-center mt-3">
      <div class="card w-96">
        <img class="card-img-top" :src="avatar" />
        <ul class="flex flex-col items-center">
          <li class="list-group-item w-full text-center">
            Usuário:
            <span class="badge bg-red-600"> {{ login }} </span>
          </li>
          <li class="list-group-item w-full text-center">
            Localização:
            <span class="badge bg-gray-600"> {{ location }} </span>
          </li>
          <li class="list-group-item w-full text-center">
            Repositórios:
            <span class="badge bg-green-400"> {{ public_repos }} </span>
          </li>
          <li class="list-group-item w-full text-center">
            Seguidores:
            <span class="badge bg-blue-700 mr-10">{{ followers }}</span>
            
            Seguindo:
            <span class="badge bg-green-700"> {{ following }} </span>
          </li>
        </ul>
        <div
          class="
            my-4
            w-full
            text-center
            flex flex-col
            justify-center
            items-center
          "
        >
          <a
            :href="html_url"
            class="btn btn-success btn-block w-1/2 mb-3"
            target="_blank"
          >
            Ver perfil</a
          >
          <a
            :href="blog"
            class="btn btn-success btn-block w-1/2 mb-5"
            target="_blank"
          >
            Ver Blog</a
          >
          <a
            class="btn btn-danger btn-block w-1/2"
            v-on:click="navigate()"
            >Voltar</a
          >
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import Navbar from "../components/Navbar.vue";
import router from "../router";
export default {
  name: "About",
  components: {
    Navbar,
  },
  data() {
    return {
      avatar: "",
      blog: "",
      followers: "",
      following: "",
      html_url: "",
      location: "",
      login: "",
      public_repos: "",
    };
  },
  created() {
    this.blog = this.$route.params.blog;
    this.avatar = this.$route.params.avatar;
    this.blog = this.$route.params.blog;
    this.followers = this.$route.params.followers;
    this.following = this.$route.params.following;
    this.html_url = this.$route.params.html_url;
    this.location = this.$route.params.location;
    this.login = this.$route.params.login;
    this.public_repos = this.$route.params.public_repos;
  },
  methods: {
    navigate() {
      router.go(-1);
    },
  },
};
</script>