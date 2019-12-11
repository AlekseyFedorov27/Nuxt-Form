<template>
  <div>
    <v-toolbar
      :extended="extended"
      :prominent="prominent"
      :dense="dense"
      :collapse="collapse"
      :flat="flat"
      :src="bg ? 'https://cdn.vuetifyjs.com/images/backgrounds/vbanner.jpg' : undefined"
      :extension-height="extensionHeight"
    >

      <v-spacer></v-spacer>

      <v-toolbar-items>
        <nuxt-link to="/options"><v-btn text >Параметры</v-btn></nuxt-link>
        <nuxt-link to="/questions"><v-btn text>Вопросы</v-btn></nuxt-link>
        <nuxt-link to="/logics"><v-btn text>Логика</v-btn></nuxt-link>
        
        <nuxt-link to="/сonditions"><v-btn text>Условия</v-btn></nuxt-link>
        <nuxt-link to="/respondents"><v-btn text >Респонденты</v-btn></nuxt-link>
        
      </v-toolbar-items>


    </v-toolbar>
  </div>
</template>

<script>
  export default {
    data: () => ({
      extended: false,
      extendedSlot: false,
      prominent: false,
      dense: false,
      collapse: false,
      flat: false,
      bg: false,
      extensionHeight: 48,
    }),
  }
</script>