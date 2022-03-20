<template>
  <div style="width: 100%; padding:10px 100px;">
        <q-chat-message
          :text="['Have you seen Quasar?']"
          sent
          text-color="white"
          bg-color="primary"
        >
          <template v-slot:name><span class="text-white">John Dee</span></template>
          <template v-slot:stamp>7 minutes ago</template>
          <template v-slot:avatar>
            <img
              class="q-message-avatar q-message-avatar--sent"
              src="https://cdn.quasar.dev/img/avatar4.jpg"
            >
          </template>
        </q-chat-message>

        <q-chat-message bg-color="amber">
          <template v-slot:name><span class="text-white">Mary</span></template>
          <template v-slot:avatar>
            <img
              class="q-message-avatar q-message-avatar--received"
              src="https://cdn.quasar.dev/img/avatar2.jpg"
            >
          </template>

          <div class="">
            Already building an app with it...
            <q-img  src="https://cdn.quasar.dev/img/discord-qeart.png" class="my-emoji"/>
          </div>

          <q-spinner-dots color="primary" size="2rem" />
        </q-chat-message>
      </div>
</template>
