<template>
  <q-page class="flex column">
    <div>
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
            <DostVerticalRight />
          </div>
        </div>
      </q-bar>
    </div>
    <div  style="flex:1; " class="bg-image flex justify-center">
      <ChatTalking />
    </div>
     <DrawerLeft />
     <DrawerRight />
     <FooterMessage />
  </q-page>
</template>

<script>
import { defineComponent } from 'vue';
import ChatTalking from 'src/components/ChatTalking.vue';
import DostVerticalRight from 'src/components/DostVerticalRight.vue';
import DrawerRight from 'src/components/DrawerRight.vue';
import { useStoreDrawer } from 'src/stores/drawerRight';
import DrawerLeft from '../components/DrawerLeft.vue';
import FooterMessage from '../components/FooterMessage.vue';

export default defineComponent({
  name: 'IndexPage',
  components: {
    DostVerticalRight,
    DrawerLeft,
    FooterMessage,
    DrawerRight,
    ChatTalking,
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

<style scoped >
  .bg-image {
    background-image: url('src/assets/background_chat.jpg');
    background-repeat: no-repeat;
    background-size: cover;
  }
  .my-emoji{
  vertical-align: middle;
  height: 2em;
  width: 2em;
  }
</style>
