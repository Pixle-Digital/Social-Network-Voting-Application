<template>
  <div>
    <b-card>
      <h2>You're their type</h2>
      <hr />

      <div class="people-container">
        <b-media
          class="person-item"
          v-for="(person, index) in peoples"
          :key="index"
        >
          <template #aside>
            <b-img
              blank
              blank-color="#ccc"
              width="64"
              alt="placeholder"
            ></b-img>
          </template>

          <h5 class="mt-0">{{ person.name }} - {{ person.age }}</h5>
          <p class="mb-0">
            {{ person.address }}
          </p>
        </b-media>
      </div>
    </b-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      peoples: [
        {
          name: "Nicole",
          age: "19",
          address: "36- Greenboro , NC",
        },
        {
          name: "Nicole",
          age: "19",
          address: "36- Greenboro , NC",
        },
        {
          name: "Nicole",
          age: "19",
          address: "36- Greenboro , NC",
        },
      ],
    };
  },
};
</script>

<style scoped>
.person-item {
  margin: 0.5rem 0;
}
</style>