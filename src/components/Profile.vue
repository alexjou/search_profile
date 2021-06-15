<template>
  <div class="flex items-center justify-center">
    <div class="card w-72">
      <img class="card-img-top" :src="user.avatar_url" />
      <ul class="flex flex-col items-center">
        <li class="list-group-item w-full text-center">
          Repositórios:
          <span class="badge bg-green-400"> {{ user.public_repos }} </span>
        </li>
        <li class="list-group-item w-full text-center">
          Seguidores:
          <span class="badge bg-blue-700">{{ user.followers }}</span>
        </li>
        <li class="list-group-item w-full text-center">
          Seguindo:
          <span class="badge bg-green-700"> {{ user.following }} </span>
        </li>
      </ul>
      <div class="my-4 w-full text-center">
        <a
          :href="user.html_url"
          class="btn btn-success btn-block"
          target="_blank"
        >
          Ver perfil</a
        >
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["user"],
};
</script>
