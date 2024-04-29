<template>
  <div class="row wrap justify-between items-start content-start q-gutter-md">
    <div class="bg-grey-1 col-lg-9 co1-12 q-mr-md">
      <StatCard />
      <ChartCard />
      <DashboardTable />
    </div>
    <div class="bg-grey-1 col-lg col">
      <ToolsCard />
    </div>
  </div>
</template>

<script setup>
import StatCard from "components/StatCards.vue";
import ToolsCard from "components/ToolsCard.vue";
import ChartCard from "components/ChartCard.vue";
import DashboardTable from "components/DashboardTable.vue";
defineOptions({
  name: "IndexPage",
});
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
</script>

<style scoped lang="scss">
.my-card {
  width: 100%;
}
</style>
