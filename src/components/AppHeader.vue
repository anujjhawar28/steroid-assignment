<template>
  <q-header class="bg-grey-1">
    <q-toolbar class="q-py-lg">
      <div class="fit row wrap justify-between items-start content-start">
        <div class="flex col-lg-6">
          <q-btn
            size="sm"
            flat
            @click="$emit('drawer-btn-click')"
            round
            dense
            icon="menu"
            color="black"
          />
          <q-toolbar-title class="text-black text-weight-bold text-h4">
            Overview
          </q-toolbar-title>
        </div>

        <div class="flex items-center hide-mobile">
          <q-icon name="notifications" size="sm" color="black" />
          <q-avatar class="q-ml-md">
            <img src="https://cdn.quasar.dev/img/avatar.png" />
          </q-avatar>
          <q-btn-dropdown
            no-caps
            unelevated
            flat
            text-color="grey"
            class="header-dropdown q-ml-md"
            label="Administrator"
          >
            <q-list>
              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>Photos</q-item-label>
                </q-item-section>
              </q-item>

              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>Videos</q-item-label>
                </q-item-section>
              </q-item>

              <q-item clickable v-close-popup>
                <q-item-section>
                  <q-item-label>Articles</q-item-label>
                </q-item-section>
              </q-item>
            </q-list>
          </q-btn-dropdown>
        </div>
      </div>
    </q-toolbar>
  </q-header>
</template>

<style scoped lang="scss">
.header-dropdown {
  color: rgb(119, 121, 122) !important;
}
</style>
