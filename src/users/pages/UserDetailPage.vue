<template>
  <div>
    <user-places-list :items="placeLists" />
  </div>
</template>

<script>
import UserPlacesList from "@/places/components/UserPlacesList.vue";

export default {
  name: "UserDetailPage",
  components: {
    UserPlacesList,
  },
  data() {
    return {
      placeLists: [
        {
          id: "p4",
          title: "Exploring New Technologies",
          description: "Stay ahead with insights into the latest tech advancements.",
          imageUrl: "https://th.bing.com/th/id/OIP.wF7Vck4BY-M4YfpBvvh4pAHaFI?w=253&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7",
        },
        {
          id: "p6",
          title: "Adapting Changes",
          description: "Discover strategies to stay resilient in a fast-evolving world.",
          imageUrl: "https://th.bing.com/th/id/OIP.GadOYLiTmxxU1GD4jJxjIAHaH-?rs=1&pid=ImgDetMain",
        },
        {
          id: "p2",
          title: "Empowering Through Knowledge",
          description: "Access resources to boost skills and build expertise.",
          imageUrl: "https://th.bing.com/th/id/R.6d965ec11ef6ac326f66d24943b464d6?rik=VgWjBKfIc6AfIQ&riu=http%3a%2f%2fdamienmarieathope.com%2fwp-content%2fuploads%2f2017%2f02%2fKnowledge.jpg&ehk=HBwe1El7LpwUqQdUmOxnng3Ya93YItSeW6%2fznYcGZnE%3d&risl=&pid=ImgRaw&r=0",
        },
        {
          id: "p3",
          title: "Future of Artificial Intelligence",
          description: "Get insights into the potential and challenges of AI.",
          imageUrl: "https://th.bing.com/th/id/OIP.DS0Il30FrmNewieHW5MJMQHaEK?rs=1&pid=ImgDetMain",
        },
        {
          id: "p5",
          title: "Next-Gen Solutions",
          description: "See what’s next in problem-solving through digital tools.",
          imageUrl: "https://th.bing.com/th/id/OIP.D2fjDJjruPidNuKk6yNZ2gHaEo?rs=1&pid=ImgDetMain",
        },
      ],
      filteredUserLists: [],
    };
  },
  methods: {
    filteredUserList() {
      this.filteredUserLists = this.placeLists.filter((place) => place.id);
    },
  },
};
</script>

<style scoped></style>
