<template>
  <q-footer style="height: 3.7em;">
    <div class="flex full-height row items-center" style="height: 200px;">
      <q-icon
        name="mdi-emoticon-outline" size="2em"
        style="flex:0; margin-left: 5px; cursor: pointer;"
      />
      <q-fab icon="mdi-paperclip" direction="up" unelevated style="flex:0; margin: 0 5px;">
        <q-fab-action color="accent" @click="onClick" icon="mdi-image" />
        <q-fab-action color="blue" @click="onClick" icon="mdi-sticker-emoji" />
        <q-fab-action color="pink" @click="onClick" icon="mdi-camera" />
        <q-fab-action color="indigo-5" @click="onClick" icon="mdi-file" />
        <q-fab-action color="info" @click="onClick" icon="mdi-account" />
      </q-fab>
      <div  style="flex:9">
        <q-input
        v-model="turnIntoPhone"
        filled dense placeholder="mensagem"/>
      </div>
      <q-icon :name="turnIntoPhone === '' ? 'mdi-microphone' : 'mdi-send'"
      size="2em" style="flex:0.5; cursor: pointer;"/>
      <!-- <q-icon name="mdi-send" size="2em" style="flex:0.5; cursor: pointer;"/> -->
    </div>
  </q-footer>
</template>

<script>
import { ref } from 'vue';

export default {
  setup() {
    const turnIntoPhone = ref('');

    return {
      onClick() {
        // console.log('Clicked on a fab action')
      },
      turnIntoPhone,
    };
  },
};
</script>
