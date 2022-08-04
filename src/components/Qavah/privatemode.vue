<template>
  <div class="">
    <b-card>
      <b-media>
        <template #aside>
          <b-img blank blank-color="#ccc" width="64" alt="placeholder"></b-img>
        </template>

        <h5 class="mt-0">Private Mode</h5>
        <p class="mb-0">Only can be seen by members you like or manage</p>
        <b-link
          >Choose who sees you
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="20"
            fill="none"
            viewBox="0 0 24 24"
            stroke="currentColor"
            stroke-width="2"
          >
            <path
              stroke-linecap="round"
              stroke-linejoin="round"
              d="M17 8l4 4m0 0l-4 4m4-4H3"
            />
          </svg>
        </b-link>
      </b-media>
    </b-card>
  </div>
</template>

<script>
export default {};
</script>

<style>
</style>