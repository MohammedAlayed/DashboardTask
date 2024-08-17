<template>
  <div class="p-3 sm:ml-64">
    <div class="p-3 border-2 border-dashed rounded-lg border-gray-700">
      <!-- Line Chart -->
      <div>
        <h3 class="font-semibold text-lg text-neutral-500">Line Chart</h3>
        <LineChart
          v-if="isCurrentPriority(Priority.FIRST)"
          @rendered="updatePriority(Priority.SECOND)"
        />
      </div>

      <!-- Donut Chart -->
      <div class="mt-7">
        <h3 class="font-semibold text-lg text-neutral-500">Donut Chart</h3>
        <DonutsChart
          v-if="isCurrentPriority(Priority.SECOND)"
          @rendered="updatePriority(Priority.THIRD)"
        />
      </div>

      <!-- Column Chart -->
      <div class="mt-7">
        <h3 class="font-semibold text-lg text-neutral-500">Column Chart</h3>
        <BarChart
          v-if="isCurrentPriority(Priority.THIRD)"
          @rendered="updatePriority(Priority.THIRD)"
        />
      </div>
    </div>
  </div>
</template>

<script>
import LineChart from "../components/LineChart.vue";
import DonutsChart from "../components/DonutsChart.vue";
import BarChart from "../components/BarChart.vue";

const Priority = {
  FIRST: 1,
  SECOND: 2,
  THIRD: 3,
};

export default {
  components: { LineChart, DonutsChart, BarChart },
  data() {
    return {
      priority: Priority.FIRST,
    };
  },
  computed: {
    Priority() {
      return Priority;
    },
  },
  methods: {
    /**
     * Updates the priority to the next value after a chart is rendered.
     * @param {number} nextPriority
     */
    updatePriority(nextPriority) {
      this.priority = nextPriority;
    },

    /**
     * Checks if the current priority level allows a specific chart to be rendered.
     * @param {number} priorityLevel
     * @returns {boolean} - True if the current priority is equal or higher
     */
    isCurrentPriority(priorityLevel) {
      return this.priority >= priorityLevel;
    },
  },
};
</script>
