<template>
  <div class="row q-gutter-lg">
    <div class="col">
      <q-card bordered class="my-card">
        <q-card-section
          class="q-pa-lg"
          v-for="(card, index) in cards"
          :key="index"
        >
          <div class="text-weight-bold q-mb-md">{{ card.heading }}</div>
          <q-item v-ripple v-for="(child, idx) in card.children" :key="idx">
            <q-item-section side>
              <q-avatar>
                <img src="https://cdn.quasar.dev/img/avatar.png" />
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label>{{ child.title }}</q-item-label>
              <q-item-label caption>{{ child.description }}</q-item-label>
            </q-item-section>
          </q-item>
        </q-card-section>
      </q-card>
    </div>
  </div>
</template>

<script setup>
const cards = [
  {
    heading: "Popular Product",
    children: [
      {
        title: "Gadget Converter",
        description: "$250",
      },
      {
        title: "Lens Camera",
        description: "$50",
      },
      {
        title: "Airpods",
        description: "$100",
      },
      {
        title: "Macbook",
        description: "$999",
      },
    ],
  },
  {
    heading: "Chat",
    children: [
      {
        title: "Debra Young Converter",
        description: "How's my prodyuct ?",
      },
      {
        title: "Dorothy Collins",
        description: "How was the meeting ?",
      },
      {
        title: "Chris Jordan",
        description: "How's employee performance ?",
      },
      {
        title: "Denise Murphy",
        description: "How was the meeting ?",
      },
    ],
  },
];
</script>

<style scoped lang="scss">
.my-card {
  width: 100%;
}
</style>
