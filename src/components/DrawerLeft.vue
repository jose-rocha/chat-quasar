<template>
  <q-drawer
      show-if-above
      bordered
      :width="350"
      :breakpoint="100"
    >
      <q-list>
        <q-item-label header class="bg-primary flex items-center justify-between no-padding"
        style="height: 3.2em;">
          <div>
            <q-avatar class="q-mx-sm" color="blue" size="2.5em" text-color="white">U</q-avatar>
            <span class="text-white">User</span>
          </div>

            <DostVerticalLeft />
        </q-item-label>

      </q-list>
      <q-separator/>
      <div style="max-width: 350px">
    <q-list bordered separator>

      <q-item clickable v-ripple v-for="(n, index) in 20" :key="index">
        <q-avatar class="q-mx-sm" color="primary" size="2.5em" text-color="white">U</q-avatar>
        <q-item-section>John Dee</q-item-section>
      </q-item>

    </q-list>
  </div>
    </q-drawer>
</template>

<script>
import { ref } from 'vue';
import DostVerticalLeft from './DostVerticalLeft.vue';

export default {
  components: { DostVerticalLeft },
  setup() {
    const iconCloseSearch = ref(false);
    return {
      iconCloseSearch,
      closeTrue() {
        // console.log('digitando');
        iconCloseSearch.value = true;
      },
    };
  },
};
</script>
