<template>
  <q-drawer
      v-model="RightDrawerOpen.drawer"
      bordered
      :width="350"
      :breakpoint="100"
      side="right"
    >
      <q-list>
        <q-item-label header class="bg-primary" style="height: 3.2em;">
          <q-icon name="mdi-close" size="1.5em"
          style="cursor: pointer;" @click="toggleCloseRightDrawer"/>
          <span class="text-white q-ml-sm">Pesquisar mensagens</span>
        </q-item-label>

         <q-input outlined dense placeholder="Pesquisar" class="q-ma-sm" @click="closeTrue">
            <template v-slot:prepend>
              <q-icon :name="iconCloseSearch === true ? 'mdi-arrow-left' : 'search' " />
            </template>
            <template v-slot:append>
              <q-icon name="mdi-close" v-if="iconCloseSearch" @click="iconCloseSearch = false"/>
            </template>
          </q-input>
      </q-list>
    </q-drawer>
</template>

<script>
import { useStoreDrawer } from 'src/stores/drawerRight';
import { ref } from 'vue';

export default {
  setup() {
    const storeDrawer = useStoreDrawer();
    const RightDrawerOpen = storeDrawer.$state;
    const iconCloseSearch = ref(false);

    return {
      RightDrawerOpen,
      toggleCloseRightDrawer() {
        RightDrawerOpen.drawer = false;
        iconCloseSearch.value = false;
      },
      iconCloseSearch,
      closeTrue() {
        // console.log('digitando');
        iconCloseSearch.value = true;
      },
    };
  },
};
</script>
