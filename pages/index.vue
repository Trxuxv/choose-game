<template>
  <Default />
</template>

<script lang="ts">
import DefaultVue from '~/components/Default.vue';
import Vue from 'vue'

export default Vue.extend({
  name: "IndexPage",
  components: { DefaultVue }
})
</script>
