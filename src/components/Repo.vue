<template>
  <div class="card card-body mb-2 w-2/3 sm:hidden">
    <div class="flex flex-row sm:hidden">
      <div class="col-md-6 sm:col-md-1">
        <a :href="repo.html_url" target="_blank">{{ repo.name }}</a>
        <h2>{{ repo.description }}</h2>
      </div>
      <div class="">
        <span class="badge bg-blue-600">Linguagem: {{ repo.language }} </span>
        <span class="badge bg-yellow-400 mx-1"
          >Stars: {{ repo.stargazers_count }}
        </span>
        <span class="badge bg-gray-600 mr-1"
          >Watch: {{ repo.watchers_count }}
        </span>
        <span class="badge bg-green-600">Forks: {{ repo.forks_count }} </span>
      </div>
    </div>    
  </div>
  <div class="hidden card mb-2 sm:w-full sm:flex sm:items-center sm:justify-center sm:text-center">
  <div class="flex flex-col">
        <a :href="repo.html_url" target="_blank">{{ repo.name }}</a>
        <h2>{{ repo.description }}</h2>
        <span class="badge bg-blue-600">Linguagem: {{ repo.language }} </span>
        <span class="badge bg-yellow-400 my-2"
          >Stars: {{ repo.stargazers_count }}
        </span>
        <span class="badge bg-gray-600"
          >Watch: {{ repo.watchers_count }}
        </span>
        <span class="badge bg-green-600 mt-2">Forks: {{ repo.forks_count }} </span>
      </div>
      </div>
</template>

<script>
export default {
  props: ["repo"],
};
</script>