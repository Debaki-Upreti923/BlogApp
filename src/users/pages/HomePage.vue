<template>
  <div>
    <UserList :users="users" />
    <div class="container">
      <div
        class="card"
        style="width: 18rem; color: white; box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2)"
      >
        <img
          src="https://th.bing.com/th/id/OIP.yKVsIan4lqU-syTmtUTF7AHaEH?rs=1&pid=ImgDetMain"
          class="card-img-top"
          alt=""
        />
        <div class="card-body">
          <h5 class="card-title">Digital Future</h5>
          <p class="card-text">
            Dive into the digital world and see what's next.
          </p>
          <a @click="goToUserDetailPage" class="btn btn-primary">Load More</a>
        </div>
      </div>
      <div
        class="card"
        style="width: 18rem; background-color:#37464e; color: white; box-shadow: 1px 2px 3px rgba(0, 0, 0, 0.2)"
      >
        <img
          src="https://c8.alamy.com/comp/2F953RY/future-technology-concept-woman-works-with-digital-screen-in-futuristic-space-3-d-illustration-2F953RY.jpg" height="155px"
          class="card-img-top"
          alt=""
        />
        <div class="card-body">
          <h5 class="card-title">Modern Challenges</h5>
          <p class="card-text">
            Find solutions to today’s pressing challenges.
          </p>
          <a @click="goToUserDetailPage" class="btn btn-primary">Load More</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import UserList from "../components/UserList.vue";
import axios from "axios";

export default {
  name: "HomePage",
  components: {
    UserList,
  },
  data() {
    return {
      message: "This is home component",
    };
  },
  methods: {
    getUserData() {
      axios
        .get("http://localhost:5000/users")
        .then((response) => {
          console.log(response.data);
          return response.data;
        })
        .catch((error) => {
          console.error("Error fetching user data:", error);
        });
    },
    goToUserDetailPage() {
      this.$router.push({ name: "UserDetailPage" });
    },
  },
  created() {
    this.getUserData();
  },
};
</script>

<style scoped>
.container {
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 5px;
  gap: 30px;
}

.card {
  background-color: #37464e;
}
</style>
