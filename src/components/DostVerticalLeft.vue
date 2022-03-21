<template>
  <div >
    <q-btn round icon="mdi-dots-vertical" size="sm" text-color="white" unelevated>
      <q-menu :offset="[180, 5]">
        <q-list dense bordered padding class="rounded-borders" style="width: 200px;">
          <q-item clickable v-ripple>
            <q-item-section>
              Item
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple >
            <q-item-section>
              Configurações
            </q-item-section>
          </q-item>

          <q-item clickable v-ripple>
            <q-item-section>
              Item
            </q-item-section>
          </q-item>
        </q-list>
      </q-menu>
    </q-btn>
  </div>
</template>
