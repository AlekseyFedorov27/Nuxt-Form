<template>
  <section >
    <Toolbars/>

      <div class="container">
        <nuxt/>
      </div>

  </section>
</template>
<script>
import Toolbars from '~/components/Toolbars.vue'

export default {
  components: {
    Toolbars
  }
  
}
</script>
<style>
body{
  font-family: 'Roboto', 'Arial Narrow', Arial, sans-serif
}
.container {
  min-width: 1000px;
  /* display: flex;
  justify-content: center; */
  /* align-items: center;
  text-align: center; */
}
</style>

