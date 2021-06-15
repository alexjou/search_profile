<template>
    <div class="card card-body mb-2 w-2/3">
        <div class="flex flex-row">
            <div class="col-md-6">
                <a :href="repo.html_url" target="_blank">{{ repo.name }}</a>
                <h2>{{ repo.description }}</h2>
            </div>
            <div class="">
                <span class="badge bg-blue-600" >Linguagem: {{ repo.language}} </span>
                <span class="badge bg-blue-600 mx-1">Stars: {{ repo.stargazers_count}} </span>
                <span class="badge bg-gray-600 mr-1">Watch: {{ repo.watchers_count }} </span>
                <span class="badge bg-green-600">Forks: {{ repo.forks_count }} </span>
            </div>
        </div>
    </div>
</template>

<script>
export default {
  props: ["repo"],
};
</script>