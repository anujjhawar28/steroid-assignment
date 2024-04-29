<template>
  <div class="row q-mt-md">
    <div class="col-12">
      <q-table
        bordered
        :rows="rows"
        :columns="columns"
        row-key="index"
        virtual-scroll
        v-model:pagination="pagination"
        :rows-per-page-options="[0]"
      >
        <template #top-left>
          <div>
            <div class="text-weight-bold">Document</div>
            <div class="description" caption>Document Tracking Information</div>
          </div>
        </template>

        <template #body-cell-status="{ row }">
          <q-btn
            v-if="row.status === 'Send'"
            outline
            rounded
            no-caps
            size="sm"
            color="green"
            class="q-mt-sm"
            :label="row.status"
          />
          <q-btn
            v-else
            outline
            rounded
            no-caps
            size="sm"
            color="red"
            class="q-mt-sm"
            :label="row.status"
          />
        </template>
        <template #top-right>
          <q-btn-dropdown
            no-caps
            unelevated
            flat
            rounded
            text-color="black"
            class="header-dropdown q-ml-md bg-grey-4"
            label="Weekly"
          >
            <q-list>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>Monthly</q-item-label>
                </q-item-section>
              </q-item>

              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>Daily</q-item-label>
                </q-item-section>
              </q-item>

              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>Yearly</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </template>
      </q-table>
    </div>
  </div>
</template>

<script setup>
import { ref } from "vue";

const columns = [
  {
    name: "name",
    required: true,
    label: "Name",
    align: "left",
    field: (row) => row.name,
    format: (val) => `${val}`,
    sortable: true,
  },
  {
    name: "file",
    align: "left",
    label: "File",
    field: "file",
    sortable: true,
  },
  {
    name: "category",
    align: "left",
    label: "Category",
    field: "category",
    sortable: true,
  },
  {
    name: "author",
    align: "left",
    label: "Author",
    field: "author",
    sortable: true,
  },
  {
    name: "status",
    align: "left",
    label: "Status",
    field: "status",
    sortable: true,
  },
];

const rows = [
  {
    name: "Annual Report",
    file: "PDF",
    category: "Property",
    author: "Diana Mathews",
    status: "Send",
  },
  {
    name: "Buisness plan",
    file: "Word",
    category: "Cryptocurrency",
    author: "Philip James",
    status: "Send",
  },
  {
    name: "Marketing Tool",
    file: "PDF",
    category: "Content Creator",
    author: "Amanda Ross",
    status: "Pending",
  },
];
</script>

<style scoped lang="scss">
.description {
  font-size: 10px;
  color: grey;
}
</style>
