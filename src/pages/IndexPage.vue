<template>
  <q-page class="flex ">
    <q-bar class="flex full-width bg-primary no-padding" style="height:2.5em">
      <div class="flex items-center justify-between full-width full-height">
        <div class="q-pl-sm">
          <q-avatar class="q-mr-sm" color="blue" size="2em" text-color="white">J</q-avatar> teste
        </div>
        <div class="flex q-pr-sm full-height items-center" style="cursor:pointer">
          <q-icon
            name="search" size="1.3em" class="q-mr-md" color="white"
            @click="toggleRightDrawer"
          />
          <DostVertical />
        </div>
      </div>
    </q-bar>
     <DrawerLeft />
     <DrawerRight />
     <FooterMessage />
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import DostVertical from 'src/components/DostVertical.vue';
import DrawerRight from 'src/components/DrawerRight.vue';
import { useStoreDrawer } from 'src/stores/drawerRight';
import DrawerLeft from '../components/DrawerLeft.vue';
import FooterMessage from '../components/FooterMessage.vue';

export default defineComponent({
  name: 'IndexPage',
  components: {
    DostVertical, DrawerLeft, FooterMessage, DrawerRight,
  },
  setup() {
    const storeDrawer = useStoreDrawer();
    const RightDrawerOpen = storeDrawer.$state;
    // const RightDrawerOpen = ref(false);
    return {
      toggleRightDrawer() {
        // console.log('RightDrawerOpen');
        RightDrawerOpen.drawer = true;
      },
    };
  },
});
</script>
