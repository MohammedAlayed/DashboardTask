<template>
  <Sidebar />
  <Dashboard />
</template>

<script>
import Sidebar from "./components/Sidebar.vue";
import Dashboard from "./views/Dashboard.vue";

export default {
  components: {
    Sidebar,
    Dashboard,
  },
};
</script>
