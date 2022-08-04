<template>
  <div>
    <b-tabs pills no-nav-style>
      <b-tab title="Likes You" active>
        <hr />

        <div class="">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            height="30"
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
          <h2>No Likes Yet</h2>
          <p>
            Give a little, get a little. Send some likes to people who've caught
            your eye!
          </p>
        </div>
      </b-tab>
      <b-tab title="You Like">
        <hr />
        <div class="peoples-container">
          <b-card
            no-body
            class="person-item"
            v-for="(person, index) in peoples"
            :key="index"
          >
            <div class="left">
              <b-avatar></b-avatar>
              <div>
                <h4 class="p-0 m-0">{{ person.name }}</h4>
                <p class="p-0 m-0">{{ person.status }}</p>
                <p class="p-0 m-0">{{ person.time }}</p>
              </div>
            </div>
            <b-button class="chat-btn">Chat</b-button>
          </b-card>
        </div>
      </b-tab>
    </b-tabs>
  </div>
</template>

<script>
export default {
  name: "favourites-component",
  data() {
    return {
      peoples: [
        {
          id: "1",
          name: "Sarah Khan",
          status: "liked",
          time: "21 mins ago",
        },
        {
          id: "2",
          name: "Sarah Khan",
          status: "liked",
          time: "21 mins ago",
        },
        {
          id: "3",
          name: "Sarah Khan",
          status: "liked",
          time: "21 mins ago",
        },
        {
          id: "4",
          name: "Sarah Khan",
          status: "liked",
          time: "21 mins ago",
        },
      ],
    };
  },
};
</script>

<style scoped>
.person-item {
  background-color: #f3f6f8;
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  padding: 0.5rem 1rem;
  margin: 0.5rem 0;
}

.person-item .left {
  display: flex;
}

.chat-btn {
  background-color: #93652b !important;
  outline: none;
  border: none;
  border-radius: 10px;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  /* padding: 1rem 2rem;  */
}

.custom-tab-btn {
  background-color: #93652b !important;
  outline: none;
  border: none;
  border-radius: 10px;
  color: #fff;
  display: flex;
  justify-content: center;
  align-items: center;
  padding: 1rem 2rem;
}
</style>