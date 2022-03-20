<template>
  <q-drawer
      show-if-above
      bordered
      :width="350"
      :breakpoint="100"
    >
      <q-list>
        <q-item-label header class="bg-primary flex items-center no-padding" style="height: 3.2em;">
           <q-avatar class="q-mx-sm" color="blue" size="2.5em" text-color="white">U</q-avatar>
           teste
        </q-item-label>

         <q-input
          outlined dense placeholder="Pesquisar uma conversa"
          class="q-ma-sm" @click="closeTrue"
          >
            <template v-slot:prepend>
              <q-icon :name="iconCloseSearch === true ? 'mdi-arrow-left' : 'search' " />
            </template>
            <template v-slot:append>
              <q-icon name="mdi-close" v-if="iconCloseSearch" @click="iconCloseSearch = false"/>
            </template>
          </q-input>
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

export default {
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
