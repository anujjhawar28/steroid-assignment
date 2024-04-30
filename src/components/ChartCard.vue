<template>
  <div class="row q-gutter-lg q-mt-sm">
    <div class="col-md col-12">
      <q-card bordered class="my-card">
        <q-card-section class="q-pa-lg">
          <div class="flex justify-between">
            <div class="text-weight-bold">Recent Workflow</div>
          </div>
          <div class="flex items-center">
            <div class="flex">
              <div class="flex q-mt-md">
                <q-icon name="trending_up" color="green" size="md" />
                <div class="text-green q-ml-xs">17 %</div>
              </div>
              <div class="chart-container">
                <canvas id="myChart" class="q-ml-xs" />
              </div>
            </div>
          </div>
        </q-card-section>
      </q-card>
    </div>

    <div class="col-md-6 col-12">
      <q-card bordered class="my-card">
        <q-card-section class="q-pa-lg">
          <div class="flex justify-between">
            <div class="text-weight-bold">Recent Marketing</div>
          </div>
          <div class="flex items-center">
            <div class="flex">
              <div class="flex q-mt-md">
                <q-icon name="trending_up" color="green" size="md" />
                <div class="text-green q-ml-xs">17 %</div>
              </div>
              <div class="chart-container">
                <canvas id="myChart1" class="q-ml-xs" />
              </div>
            </div>
          </div>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script setup>
import { onMounted } from "vue";

const cards = [
  {
    heading: "Document",
    icon: "inbox",
    stat: "146.000",
  },
  {
    heading: "Contact",
    icon: "perm_contact_calendar",
    stat: "1400",
  },
  {
    heading: "Email",
    icon: "email",
    stat: "150.700",
  },
];

onMounted(() => {
  const ctx1 = document.getElementById("myChart");
  new Chart(ctx1, {
    type: "bar",
    data: {
      labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange", "black"],
      datasets: [
        {
          label: "# of Votes",
          data: [12, 19, 3, 5, 2, 3, 50],
          borderWidth: 1,
        },
      ],
    },
    options: {
      scales: {
        y: {
          beginAtZero: true,
        },
      },
    },
  });

  const ctx2 = document.getElementById("myChart1");
  new Chart(ctx2, {
    type: "line",
    data: {
      labels: ["Red", "Blue", "Yellow", "Green", "Purple", "Orange", "black"],
      datasets: [
        {
          label: "My First Dataset",
          data: [65, 59, 80, 81, 56, 55, 40, 100],
          fill: false,
          borderColor: "rgb(75, 192, 192)",
          tension: 0.1,
        },
      ],
    },
    options: {
      scales: {
        y: {
          beginAtZero: true,
        },
      },
    },
  });
});
</script>

<style scoped lang="scss">
.my-card {
  width: 100%;
}
</style>
