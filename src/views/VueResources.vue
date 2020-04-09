<template>
  <resources-list />
</template>
<script>
import resourcesList from '../components/ResourcesList.vue';

export default {
  name: 'vueResources',
  components: {
    ResourcesList: resourcesList
  },
  data() {
    return {
      vueResources: [
        { name: 'Vue.js', url: 'https://vuejs.org', cost: 'free' },
        {
          name: 'Vue Mastery',
          url: 'https://vuemastery.com',
          cost: 'some free'
        },
        {
          name: 'Vue @ LaraCasts',
          url: 'https://laracasts.com/series/learn-vue-2-step-by-step',
          cost: 'some free'
        },
        {
          name: 'Pluralsight',
          url: 'https://www.pluralsight.com/search?q=vue.js',
          cost: 'free'
        }
      ]
    };
  }
};
</script>
