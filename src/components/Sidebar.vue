<template>
  <aside
    class="fixed top-0 left-0 z-40 w-48 h-screen transition-transform -translate-x-full sm:translate-x-0"
  >
    <div class="h-full px-3 py-4 overflow-y-auto bg-gray-800">
      <ul class="space-y-2 font-medium">
        <li>
          <a
            href="#"
            class="flex items-center p-2 rounded-lg text-white hover:bg-gray-700 group"
          >
            <LayoutDashboard
              class="w-5 h-5 transition duration-75 text-gray-400  group-hover:text-white"
            />
            <span class="ms-3">Dashboard</span>
          </a>
        </li>
      </ul>
    </div>
  </aside>
</template>

<script setup>
import { LayoutDashboard } from "lucide-vue-next";
</script>
