<template>
	<div>
		<resources-list />
	</div>
</template>
<script>
import resourcesList from '../components/ResourcesList.vue';

export default {
	name: 'vueResources',
	components: {
		ResourcesList: resourcesList
	}
};
</script>
