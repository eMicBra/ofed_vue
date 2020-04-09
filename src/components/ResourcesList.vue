<style>
.isFree {
  background-color: rgb(240, 161, 240);
}
</style>

<template>
  <div>
    <h3>Vue.js Resources</h3>
    <ul>
      <li
        v-for="(resource, index) in vueResources"
        :key="index"
        :class="{ isFree: resource.cost == 'free' }"
        :title="resource.cost"
      >
        <a :href="resource.url">{{ resource.name }}</a>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'ResourcesList',
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
