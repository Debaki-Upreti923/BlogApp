<template>
  <header class="main-header">
    <h1 class="main-navigation__title">
      <router-link to="/">PostSphere</router-link>
    </h1>
    <nav class="main-navigation__header-nav">
      <ul class="nav-links">
        <!-- Always show these links -->
        <li>
          <router-link to="/">Home</router-link>
        </li>

        <!-- Show these links only if the user is authenticated -->
        <li v-if="isAuthenticated" id="my-places">
          <router-link to="/users/1">MY PLACES</router-link>
        </li>
        <li v-if="isAuthenticated" id="add-place">
          <router-link to="/places/new">ADD PLACE</router-link>
        </li>

        <!-- Show this link if the user is NOT authenticated -->
        <li v-if="!isAuthenticated" id="authenticate">
          <router-link to="/auth">Sign In</router-link>
        </li>

        <!-- Show this button if the user is authenticated -->
        <li v-if="isAuthenticated" id="logout">
          <button @click="logoutHandler" id="logout-button">LOGOUT</button>
        </li>
      </ul>
    </nav>
  </header>
</template>

<script>
export default {
  name: "HeaderNavigation",
  
};
</script>

<style scoped>
.main-header {
  width: 100%;
  height: 5rem;
  display: flex;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  background: linear-gradient(45deg, #3498db, #8e44ad); /* Attractive gradient of blue and purple */
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  padding: 0 2rem;
  z-index: 5;
  border-bottom: 3px solid #f39c12; /* Subtle orange accent */
}

main {
  margin-top: 5rem;
}

.main-navigation__menu-btn {
  width: 3rem;
  height: 3rem;
  background: transparent;
  border: none;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  margin-right: 2rem;
  cursor: pointer;
}

.main-navigation__menu-btn span {
  display: block;
  width: 3rem;
  height: 2.5px;
  background: white;
}

.main-navigation__title {
  color: white;
  font-family: 'Helvetica Neue', sans-serif;
  font-weight: bold;
  font-size: 2.5rem;
}

.main-navigation__title a {
  text-decoration: none;
  color: white;
}

.main-navigation__header-nav {
  display: none;
}

.nav-links {
  list-style: none;
  margin: 0;
  padding: 0;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.nav-links li {
  margin: 1rem;
}

.nav-links a {
  border: 1px solid transparent;
  color: white;
  text-decoration: none;
  padding: 0.8rem 1.2rem;
  border-radius: 5px;
  font-weight: bold;
}

.nav-links a:hover,
.nav-links a:active,
.nav-links a.active {
  background-color: #f39c12; /* Bright orange on hover for contrast */
  color: #2c3e50; /* Dark text on hover for readability */
}

.nav-links button {
  cursor: pointer;
  border: 1px solid white;
  color: white;
  background: transparent;
  padding: 0.8rem 1.2rem;
  font: inherit;
  border-radius: 5px;
}

.nav-links button:focus {
  outline: none;
}

.nav-links button:hover,
.nav-links button:active {
  background-color: #f39c12;
  color: #2c3e50;
}

@media (min-width: 768px) {
  .nav-links {
    flex-direction: row;
  }

  .nav-links li {
    margin: 0 1rem;
  }

  .nav-links a {
    color: white;
    text-decoration: none;
    padding: 0.8rem 1.5rem;
  }

  .nav-links button {
    border: 1px solid white;
    color: white;
    background: transparent;
  }

  .nav-links button:hover,
  .nav-links button:active {
    background: #f39c12;
    color: #2c3e50;
  }
}

@media (min-width: 768px) {
  .main-navigation__menu-btn {
    display: none;
  }

  .main-navigation__header-nav {
    display: block;
  }
}

@media (min-width: 768px) {
  .main-header {
    justify-content: space-between;
  }
}
</style>