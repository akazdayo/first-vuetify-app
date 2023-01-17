<template>
  <v-app>
    <v-app-bar app color="green" dark>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-app-bar-title>アプリ</v-app-bar-title>
    </v-app-bar>

    <v-navigation-drawer v-model="drawer" absolute temporary>
      <v-list nav dense>
        <v-list-item-group>
          <v-list-item v-for="item in listItems" :key="item.id">
            <v-list-item-title>{{ item.text }}</v-list-item-title>
          </v-list-item>
        </v-list-item-group>
      </v-list>
    </v-navigation-drawer>
    <v-main>
      <v-btn v-for=" item in btn " @click="currentNum = item">{{ item }}</v-btn>

      <v-container label="ねこ">
        {{ currentNum }}
      </v-container>
    </v-main>
  </v-app>
</template>

<script lang="ts">
export default {
  name: "App",
  data: () => ({
    drawer: false,
    currentNum: 0,
    listItems: [
      {
        id: 1,
        text: "foo",
      },
      {
        id: 2,
        text: "bar",
      },
      {
        id: 3,
        text: "fizz",
      },
      {
        id: 4,
        text: "buzz",
      },
    ],
    btn: [...Array<number>(200)].map((_: number, i: number) => i + 1),
  }),
};
</script>