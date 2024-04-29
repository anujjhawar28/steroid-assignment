<template>
  <q-scroll-area
    class="fit q-pa-lg-md sidebar"
    :horizontal-thumb-style="{ opacity: 0 }"
  >
    <div class="main-logo">CRM.io</div>
    <div class="q-my-md">
      <q-btn
        push
        padding="md"
        no-caps
        color="primary"
        text-color="white"
        label="Dashboard"
        size="lg"
        icon="dashboard"
        class="dashboard"
        style="width: 100%"
      />
    </div>
    <q-list padding>
      <div v-for="(menu, index) in sideMenu" :key="index">
        <div class="menu-heading">{{ menu.mainheading }}</div>
        <q-item
          clickable
          v-ripple
          v-for="(child, idx) in menu.children"
          :key="idx"
        >
          <q-item-section>
            <div class="flex items-center">
              <q-icon :name="child.icon" size="xs" />
              <span class="q-ml-md">{{ child.label }}</span>
            </div>
          </q-item-section>
        </q-item>
        <q-separator dark class="q-my-md" v-if="index < sideMenu.length - 1" />
      </div>
    </q-list>
  </q-scroll-area>
</template>

<script setup>
const sideMenu = [
  {
    mainheading: "Managment",
    children: [
      {
        icon: "inbox",
        label: "Document",
      },
      {
        icon: "perm_contact_calendar",
        label: "Contact",
      },
      {
        icon: "shopping_cart",
        label: "Prospect",
      },
      {
        icon: "autorenew",
        label: "Workflow",
      },
    ],
  },
  {
    mainheading: "Connection",
    children: [
      {
        icon: "chat",
        label: "Chat Integration",
      },
      {
        icon: "description",
        label: "Marketing Automation",
      },
      {
        icon: "email",
        label: "Email Integration",
      },
    ],
  },
  {
    mainheading: "Customer",
    children: [
      {
        icon: "paid",
        label: "Transaction",
      },
      {
        icon: "engineering",
        label: "Maintenance",
      },
    ],
  },
];
</script>

<style scoped lang="scss">
.sidebar {
  .main-logo {
    color: rgb(211, 150, 111);
    font-style: italic;
    font-size: 20px;
    margin-left: 20px;
  }
  .dashboard {
    background-color: #3963ad !important;
    font-size: 16px !important;
    border-radius: 20px;
  }
  .menu-heading {
    color: #496082 !important;
    font-size: 16px;
    margin-left: 20px;
    padding: 10px 0px !important;
  }
}
</style>
