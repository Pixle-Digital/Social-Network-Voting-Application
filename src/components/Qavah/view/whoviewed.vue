<template>
  <div>
    <h2>Who viewed your profile</h2>
    <p>Make the most of match by trying out these profile-enhancing-powerups</p>

    <div class="people-container">
      <b-card
        class="person-item"
        v-for="(person, index) in peoples"
        :key="index"
      >
        <b-avatar></b-avatar>
        <div>
          <div class="title">{{ person.name }}</div>
          <div class="status">{{ person.status }}</div>
          <div class="time">{{ person.time }}</div>
        </div>

        <div class="actions">
          <!-- Heart -->
          <b-button variant="empty">
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
                d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z"
              />
            </svg>
          </b-button>

          <!-- Star -->
          <b-button variant="empty">
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
                d="M11.049 2.927c.3-.921 1.603-.921 1.902 0l1.519 4.674a1 1 0 00.95.69h4.915c.969 0 1.371 1.24.588 1.81l-3.976 2.888a1 1 0 00-.363 1.118l1.518 4.674c.3.922-.755 1.688-1.538 1.118l-3.976-2.888a1 1 0 00-1.176 0l-3.976 2.888c-.783.57-1.838-.197-1.538-1.118l1.518-4.674a1 1 0 00-.363-1.118l-3.976-2.888c-.784-.57-.38-1.81.588-1.81h4.914a1 1 0 00.951-.69l1.519-4.674z"
              />
            </svg>
          </b-button>

          <!-- Close -->
          <b-button variant="empty">
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
                d="M6 18L18 6M6 6l12 12"
              />
            </svg>
          </b-button>
        </div>
      </b-card>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      peoples: [
        {
          id: "1",
          name: "Tiffany Doll",
          status: "viewed",
          time: "23 mins ago",
        },
        {
          id: "2",
          name: "Tiffany Doll",
          status: "viewed",
          time: "23 mins ago",
        },
        {
          id: "3",
          name: "Tiffany Doll",
          status: "viewed",
          time: "23 mins ago",
        },
      ],
    };
  },
};
</script>

<style scoped>
.person-item {
  background-color: #f3f6f8;
  margin: 0.5rem 0;
}
</style>