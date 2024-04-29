<template>
  <div class="row q-gutter-lg">
    <div class="col-md col-xs-12" v-for="(card, index) in cards" :key="index">
      <q-card bordered class="my-card">
        <q-card-section class="q-pa-lg">
          <div class="flex justify-between">
            <div class="text-weight-bold">{{ card.heading }}</div>
            <q-btn outline round color="primary" :icon="card.icon" />
          </div>
          <div class="q-mt-md text-h5 text-weight-bolder">
            {{ card.stat }}
          </div>
          <div class="flex items-center q-mt-lg">
            <div class="flex items-center">
              <q-icon name="trending_up" color="green" size="md" />
              <div class="text-green q-ml-xs">17 %</div>
              <div class="q-ml-md">Since Last week</div>
            </div>
          </div>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script setup>
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
